# A Journey into Cloud-Native Earth Observation <!--{ as="img" mode="hero" src="https://images.unsplash.com/photo-1633421878925-ac220d8f6e4f?q=80&w=1760&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" }-->

## Visualizing GeoZarr
In this story, we'll explore client-side rendered GeoZarr in Jupyter Notebooks and in the browser, using the same underlying technology. 

We'll start by connecting to a catalog of Sentinel-2 imagery, find a specific scene that catches our interest, and then—using GeoZarr and [EOxElements](https://github.com/EOX-A/EOxElements) based on the latest [OpenLayers dev release](https://www.npmjs.com/package/ol/v/10.7.1-dev.1768898466014) we can visualize an item in the browser using web components, and [ipyeoxelements](https://github.com/EOX-A/EOxElements-Jupyter) in a Python environment. We'll stream that high-resolution data directly onto an interactive map.

> **Try it yourself:** You can follow along with the code in this story by running the [Jupyter Notebook](https://github.com/EOPF-Explorer/eodash-assets/blob/main/narratives/geozarr/rendering-zarr-with-ipyeoxelements.ipynb).

## Gathering Our Tools

We'll need `httpx` to communicate with the outside world (the API) and `ipyeoxelements`, our lens for viewing the geospatial data.

```python
import httpx
import json
from ipyeoxelements import EOxMap, EOxLayercontrol
from ipywidgets import HBox, Layout
```

## Selecting the data source

Here, we define our data source, the EOPF-Explorer STAC API, specifically the `sentinel-2-l2a` collection.

```python
stac_endpoint = "https://api.explorer.eopf.copernicus.eu/stac/"
s3_endpoint = "https://s3.explorer.eopf.copernicus.eu/"
collection_id = "sentinel-2-l2a"
```

## Surveying the Landscape

First, let's take a look by querying the collection metadata, to get a sense of what kind of data is available to us.


```python
  collection = httpx.get(f"{stac_endpoint}collections/{collection_id}").json()
  print(json.dumps(collection, indent=4))
```

## Finding a Hidden Gem

Now, we dive into the catalog to find a specific scene. We'll query for a Sentinel-2 scene over Venice, Italy with minimal cloud cover to examine closely.


```python
#  Venice, Italy bbox
venice_bbox = ",".join(["11.858994964808403", "44.099770918209835", "12.936097556086393", "45.10721083440407"])
items_response = httpx.get(
    f"{stac_endpoint}search",
    params={
        "collection": collection_id,
        "filter": "eo:cloud_cover<=10",
        "bbox": venice_bbox,
        "limit": 10
    }
).json()
item = items_response.get("features", [])[7]
print(f"Fetched item: {item['id']}")
```
Fetched item: S2A_MSIL2A_20251107T100231_N0511_R122_T32TQR_20251107T115310


## Preparing the View

With our item identified, we need to translate it into something our map can understand. We'll initialize a GeoZarr Tile layer and add the EOxCloudless Terrain baselayer.


```python
def get_geozarr_store(item):
    """Construct the GeoZarr URL from the STAC item links."""
    for link in item["links"]:
        if link["rel"] == "store":
            print(f"Zarr store link: {link['href']}")
            return link["href"]


layers = []

item_id = item["id"]
zarr_url = get_geozarr_store(item)

layers = [
    {
        "type": "Tile",
        "properties": {
            "id": "terrain-light",
            "title": "Terrain Light",
        },
        "source": {
            "type": "XYZ",
            "url": "https://s2maps-tiles.eu/wmts/1.0.0/terrain-light_3857/default/g/{z}/{y}/{x}.jpeg",
            "projection": "EPSG:3857",
        },
    },
    {
        "type": "WebGLTile",
        "properties": {
            "id": f"geozarr-{item_id}",
            "title": item_id,
            "layerControlExpand": True,
        },
        "source": {
            "type": "GeoZarr",
            "url": zarr_url,
            "group": "measurements/reflectance",
            "bands": ["b04", "b03", "b02"],  # true color composite
        },
        "style": {
            "gamma": 1.5,
            "color": [
                "color",
                ["interpolate", ["linear"], ["band", 1], 0, 0, 0.5, 255],
                ["interpolate", ["linear"], ["band", 2], 0, 0, 0.5, 255],
                ["interpolate", ["linear"], ["band", 3], 0, 0, 0.5, 255],
                [
                    "case",
                    ["==", ["+", ["band", 1], ["band", 2], ["band", 3]], 0],
                    0,
                    1,
                ],
            ],
        },
    },
]
```
Zarr store link: https://s3.explorer.eopf.copernicus.eu/esa-zarr-sentinel-explorer-fra/tests-output/sentinel-2-l2a/S2A_MSIL2A_20251107T100231_N0511_R122_T32TQR_20251107T115310.zarr


## The Reveal

Finally, we bring it all together. We create our map and layer control widgets and arrange them side-by-side, just like laying out a map on a table next to our field notes.


```python
MAP_ID = "eopf-explorer-map"

map_widget = EOxMap(
    id=MAP_ID,
    layers=layers,
    center=[1362404,5572880],
    zoom=10,
    layout=Layout(height="600px", flex="2"),
    version="2.1.0-dev.1",
)

layer_control = EOxLayercontrol(
    for_=f"#{MAP_ID}",
    tools=["config"],
    layout=Layout(height="600px", flex="1", overflow="auto"),
)

# Display map and layer control side by side
HBox([map_widget, layer_control], layout=Layout(width="100%"))
```
<iframe src="https://raw.githack.com/EOPF-Explorer/eodash-assets/main/narratives/geozarr/eox-map-layercontrol.html" style="width: 100%; height: 600px; border: 1px solid #ccc;"></iframe>

## Tour <!--{ as="eox-map" mode="tour" }-->
### Replicating in the Browser  <!--{ layers='[{"type":"Tile","properties":{"id":"terrain-light","title":"Terrain Light"},"source":{"type":"XYZ","url":"https://s2maps-tiles.eu/wmts/1.0.0/terrain-light_3857/default/g/{z}/{y}/{x}.jpeg","projection":"EPSG:3857"}},{"type":"WebGLTile","properties":{"id":"geozarr-layer","title":"Sentinel-2 GeoZarr"},"source":{"type":"GeoZarr","url":"https://s3.explorer.eopf.copernicus.eu/esa-zarr-sentinel-explorer-fra/tests-output/sentinel-2-l2a/S2A_MSIL2A_20251107T100231_N0511_R122_T32TQR_20251107T115310.zarr","group":"measurements/reflectance","bands":["b04","b03","b02"]},"style":{"gamma":1.5,"color":["color",["interpolate",["linear"],["band",1],0,0,0.5,255],["interpolate",["linear"],["band",2],0,0,0.5,255],["interpolate",["linear"],["band",3],0,0,0.5,255],["case",["==",["+",["band",1],["band",2],["band",3]],0],0,1]]}}]' zoom="10" center='[12.4, 45.2]' animationOptions='{"duration": 2500}' }-->

While the Python environment is great for exploration, sharing our discoveries often happens on the web. We can replicate this exact setup using standard HTML and the `EOxElements` web components, bringing the power of cloud-native GeoZarr data directly to the browser.

### The Power of Web Components <!--{ zoom="11" center='[12.4, 45.2]' animationOptions='{"duration": 2500}' }-->

We use `eox-map` to render the map and `eox-layercontrol` for layer management. These are standard custom elements that work in any modern browser. Notice how the map renders the same GeoZarr data we explored in Python, streaming tiles on demand.

### Seamless Integration <!--{ zoom='12' center='[12.3155, 45.4408]' animationOptions='{"duration": 2500}' }-->

The beauty of this approach is the seamless transition. In fact, this entire interactive narrative is rendered using the `<eox-storytelling>` element, which parses this Markdown file and controls the map state. The layer configuration—the source URL, the bands, the styling—is identical to our Python dictionary. This means you can prototype in a notebook and deploy to the web without rewriting your logic or converting data.

### Structuring the View <!--{ zoom='12' center='[12.5375, 45.4345]' animationOptions='{"duration": 2500}' }-->

To achieve the side-by-side layout we saw earlier with Python's `HBox`, we use the `<eox-layout>` component. It provides a flexible grid system, allowing us to place the layer control on the left and the map on the right, creating a professional dashboard feel with minimal CSS.

## The Code Implementation

Here is the complete HTML code to build this view. You can copy this into an `index.html` file and run it in any web server.

```html
<!-- Import the EOxElements -->
<script type="module">
  import "@eox/map/dist/eox-map.js";
  import "@eox/layercontrol/dist/eox-layercontrol.js";
  import "@eox/layout/dist/eox-layout.js";

  // Configure the map after the DOM is ready
  const map = document.querySelector("eox-map#story-map");
  
  // Define the layers (same structure as Python)
  const layers = [
    {
      "type": "Tile",
      "properties": {
        "id": "terrain-light;:;EPSG:3857",
        "title": "Terrain Light",
      },
      "source": {
        "type": "XYZ",
        "url": "https://s2maps-tiles.eu/wmts/1.0.0/terrain-light_3857/default/g/{z}/{y}/{x}.jpeg",
        "projection": "EPSG:3857",
      },
    },
    {
      "type": "WebGLTile",
      "properties": {
        "id": "geozarr-layer",
        "title": "Sentinel-2 GeoZarr",
        "layerControlExpand": true,
      },
      "source": {
        "type": "GeoZarr",
        "url": "https://s3.explorer.eopf.copernicus.eu/esa-zarr-sentinel-explorer-fra/tests-output/sentinel-2-l2a/S2A_MSIL2A_20251107T100231_N0511_R122_T32TQR_20251107T115310.zarr",
        "group": "measurements/reflectance",
        "bands": ["b04", "b03", "b02"],
      },
      "style": {
        "gamma": 1.5,
        "color": [
          "color",
          ["interpolate", ["linear"], ["band", 1], 0, 0, 0.5, 255],
          ["interpolate", ["linear"], ["band", 2], 0, 0, 0.5, 255],
          ["interpolate", ["linear"], ["band", 3], 0, 0, 0.5, 255],
          [
            "case",
            ["==", ["+", ["band", 1], ["band", 2], ["band", 3]], 0],
            0,
            1,
          ],
        ],
      },
    }
  ];

  map.layers = layers;
  map.center = [12.3155, 45.4408];
  map.zoom = 10;
</script>

<!-- The Layout: 12-column grid system -->
<eox-layout>
    <!-- Layer Control: Takes up 4 columns (left side) -->
    <eox-layout-item x="0" y="0" w="4" h="12">
        <eox-layercontrol for="eox-map#story-map"></eox-layercontrol>
    </eox-layout-item>

    <!-- Map: Takes up 8 columns (right side) -->
    <eox-layout-item x="4" y="0" w="8" h="12">
        <eox-map id="story-map" style="width: 100%; height: 600px;"></eox-map>
    </eox-layout-item>
</eox-layout>
```


## Learn More

Explore these resources to expand your journey into cloud-native geospatial technologies, from client-side visualization to server-side rendering and full dashboard creation:

*   [EOxElements Documentation](https://eox-elements.eox.at/) – Comprehensive guide to the web components library powering modern geospatial visualization
*   [EOPF Explorer](https://explorer.eopf.copernicus.eu/) – Interactive platform for exploring Sentinel data with cloud-native technologies
*   [GeoZarr Specification](https://github.com/zarr-developers/geozarr-spec) – Technical specification for cloud-optimized geospatial data
*   [OpenLayers Examples](https://openlayers.org/en/latest/examples/) – Rich collection of mapping examples and patterns to extend your applications
*   [TiTiler EOPF](https://titiler.eopf.copernicus.eu/) – Server-side rendering and dynamic tile generation for cloud-native geospatial data
*   [EoDash](https://eodash.org/) – Create full-fledged interactive dashboards for Zarr and other geospatial data with rich visualization capabilities
*   [Discourse Community](https://discourse.eox.at/) – Join discussions, ask questions, and share your geospatial discoveries with the community
