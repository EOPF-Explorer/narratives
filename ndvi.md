# Unveiling the Green: Visualizing NDVI from Zarr <!--{ as="img" mode="hero" src="https://custom-scripts.sentinel-hub.com/custom-scripts/sentinel-2/ndvi/fig/fig1.png" }-->
#### Showing the classical NDVI example powered by the Zarr file format. Scroll down to get started! <!--{ style="font-size:1rem;opacity:0.7;margin-top:1rem;" }-->

## See the health of plants from space <!-- { style="margin-top: 7rem" } -->

Have you ever wondered how we can see the health of plants from space? It's not magic, it's science! Plants, like all living things, interact with light in unique ways. By observing these interactions, especially with satellites orbiting our planet, we can unlock a wealth of information about vegetation health, growth, and even drought stress.

This is where the Normalized Difference Vegetation Index, or NDVI, comes into play. It's a simple yet powerful tool used by scientists, farmers, and environmentalists worldwide to monitor plant vigor.

<div style="height: 7rem"></div>

## Sentinel Bands <!--{ as="eox-map" class="overlay-br" mode="tour" }-->
Copernicus data 2026. <!--{ style="opacity: 0.75; font-size: 1rem;" }-->

### <!--{ layers='[{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a-staging/items/S2B_MSIL2A_20260225T095029_N0512_R079_T33TVF_20260225T141422/tiles/WebMercatorQuad/{z}/{x}/{y}.png?variables=/measurements/reflectance:b04&variables=/measurements/reflectance:b03&variables=/measurements/reflectance:b02&rescale=0,1&color_formula=gamma rgb 1.3, sigmoidal rgb 6 0.1, saturation 1.2"}}]' center=[14.2,40.8] zoom="12" animationOptions="{duration:500}" }-->
#### The world in colors
To understand NDVI, we first need to talk about light. We see the world in colors like red, green, and blue – this is called the visible spectrum. But there's more to light than meets the eye. Plants, for instance, have a very distinct relationship with red light and near-infrared (NIR) light.

Think of a healthy plant: it absorbs most of the red light from the sun for photosynthesis, using that energy to grow. But it strongly reflects near-infrared light. It's almost like a plant's way of saying, "I'm busy photosynthesizing, here's some NIR light back!"

Conversely, unhealthy or sparse vegetation will absorb less red light and reflect less NIR light. It's this contrast between absorbed red and reflected NIR that forms the basis of NDVI.

### <!--{ layers='[{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a-staging/items/S2B_MSIL2A_20260225T095029_N0512_R079_T33TVF_20260225T141422/tiles/WebMercatorQuad/{z}/{x}/{y}.png?expression=(/measurements/reflectance:b08-/measurements/reflectance:b04)/(/measurements/reflectance:b08%2b/measurements/reflectance:b04)&rescale=-1,1&colormap_name=rdylgn"}}]' center=[14.2,40.8] zoom="12" animationOptions="{duration:500}" }-->

#### Server-side NDVI with TiTiler

For our NDVI calculation, we'll focus on two key bands from Sentinel-2:
**Band 4 (B04): Red light** and **Band 8 (B08): Near-Infrared (NIR) light**

Calculating NDVI is surprisingly straightforward. It's a simple ratio that helps us quantify the difference between NIR and Red reflectance. The formula looks like this:

**NDVI = (NIR - Red) / (NIR + Red)**

Or, using our Sentinel-2 bands:

**NDVI = (B08 - B04) / (B08 + B04)**

What you see here is **server-side rendering**: the [TiTiler](https://github.com/EOPF-Explorer/titiler-eopf) API evaluates the NDVI expression on the server, applies the `RdYlGn` colormap, and returns ready-to-display PNG tiles. This approach uses `B08` (10m resolution, 842 nm) as the NIR band.

> **Note:** Sentinel-2 offers two NIR bands — **B08** (10 m, 842 nm, broad) and **B8A** (20 m, 865 nm, narrow). Both are valid for NDVI. This story uses B08 for the server-side approach and B8A for the client-side approach below, illustrating the trade-off between spatial resolution and spectral precision.

### <!--{ layers='[{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a-staging/items/S2B_MSIL2A_20260225T095029_N0512_R079_T33TVF_20260225T141422/tiles/WebMercatorQuad/{z}/{x}/{y}.png?expression=(/measurements/reflectance:b08-/measurements/reflectance:b04)/(/measurements/reflectance:b08%2b/measurements/reflectance:b04)&rescale=-1,1&colormap_name=rdylgn"}}]' center=[14.5,40.9] zoom="10" animationOptions="{duration:2500}" }-->

#### Zooming out over the Campania region

Let's zoom out to see the full picture. Notice how the server-rendered NDVI tiles load seamlessly as we change the view — each tile is a lightweight PNG delivered by the API, making navigation feel instant even over large areas.

The agricultural plains inland glow bright green, while the volcanic slopes of Vesuvius and the rocky Amalfi coastline show lower NDVI values. This regional overview is where server-side rendering really shines.

### <!--{ layers='[{"type":"Tile","properties":{"id":"terrain-light","title":"Terrain Light"},"source":{"type":"XYZ","url":"https://s2maps-tiles.eu/wmts/1.0.0/terrain-light_3857/default/g/{z}/{y}/{x}.jpeg","projection":"EPSG:3857"}},{"type":"WebGLTile","properties":{"id":"geozarr-ndvi","title":"NDVI (GeoZarr client-side)"},"source":{"type":"GeoZarr","url":"https://s3.explorer.eopf.copernicus.eu/esa-zarr-sentinel-explorer-fra/tests-output/sentinel-2-l2a-staging/S2B_MSIL2A_20260225T095029_N0512_R079_T33TVF_20260225T141422.zarr","group":"measurements/reflectance","bands":["b04","b8a"]},"style":{"color":["interpolate",["linear"],["/",["-",["band",2],["band",1]],["+",["band",2],["band",1]]],-0.2,["color",165,0,38],0,["color",255,255,191],0.3,["color",120,190,50],0.6,["color",0,128,0],0.9,["color",0,80,0]]}}]' center=[14.5,40.9] zoom="10" animationOptions="{duration:500}" }-->

#### Client-side NDVI with GeoZarr

Now for a fundamentally different approach: instead of asking a server to compute and render the tiles, we stream the **raw Zarr data** directly from object storage (S3) into the browser. [OpenLayers](https://openlayers.org/)' `GeoZarr` source fetches the data chunks on demand, and the NDVI calculation happens entirely on your GPU via WebGL.

This client-side rendering uses `B8A` (20 m, 865 nm narrow-band NIR), which offers better spectral definition for vegetation indices. Because the browser has direct access to the raw reflectance values, you can change band combinations, color scales, or thresholds instantly — no round-trip to a server required.

## Here's how we built this <!-- { style="margin-top: 7rem" } -->

This story demonstrates **two complementary ways** to visualize NDVI from Zarr data — server-side and client-side — each with distinct trade-offs. Want to build your own? Here's everything you need to get started.

### 🖥️ Approach 1: Server-side rendering with TiTiler

**[titiler-eopf](https://github.com/EOPF-Explorer/titiler-eopf)** is an open-source tile server that reads Zarr stores, evaluates band math expressions, and returns pre-rendered PNG tiles over simple HTTP endpoints. The live API serving this demo is available at:

**`https://api.explorer.eopf.copernicus.eu/raster/`**

The server-side NDVI you saw earlier is **[dynamically rendered](https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2B_MSIL2A_20260225T095029_N0512_R079_T33TVF_20260225T141422/WebMercatorQuad/map.html?expression=(/measurements/reflectance:b08-/measurements/reflectance:b04)/(/measurements/reflectance:b08%2b/measurements/reflectance:b04)&rescale=-1,1&colormap_name=rdylgn)** — no preprocessing needed. The NDVI calculation `(B08-B04)/(B08+B04)` is processed in real-time for any date and location in the archive.

**Pros:** Works in any browser (no WebGL required), server handles all computation and colormapping, simple XYZ tile integration.  
**Cons:** Requires server infrastructure, each style or parameter change triggers a new tile request.

### 🌐 Approach 2: Client-side rendering with GeoZarr + OpenLayers

The client-side approach streams **raw Zarr data** directly from object storage to the browser. [OpenLayers](https://openlayers.org/)' `WebGLTile` layer with the `GeoZarr` source fetches data chunks on demand, and all band math and styling happens on the GPU via WebGL expressions.

The Zarr store URL for any item follows the pattern:  
**`https://s3.explorer.eopf.copernicus.eu/esa-zarr-sentinel-explorer-fra/tests-output/sentinel-2-l2a/{ITEM_ID}.zarr`**

The [STAC API](https://api.explorer.eopf.copernicus.eu/stac/) provides the store URL via the `store` link relation on each item, so you can discover it programmatically.

**Pros:** No server infrastructure beyond S3, NDVI computed on the GPU, instant re‑rendering when you change bands/colors/thresholds.  
**Cons:** Requires a WebGL-capable browser, transfers raw data (higher bandwidth), more client-side code.

> **⚠️ Bandwidth note:** The current Zarr stores encode reflectance values as **float32** (4 bytes per pixel), which drives higher data transfer when streaming to the browser compared to uint16 or uint8 encodings. Work is underway in the Zarr community to support more compact encodings — see the [Zarr codecs extension discussion](https://github.com/zarr-developers/zarr-extensions/issues/42) for progress.

> **Learn more:** Try the [interactive OpenLayers NDVI tutorial](https://explorer.eopf.copernicus.eu/software-services/ol/ndvi) with adjustable color scales and real-time parameter tweaking.

### ⚖️ Comparison at a glance

| Aspect | Server-side (TiTiler) | Client-side (GeoZarr) |
|---|---|---|
| Rendering | Server computes & returns PNG tiles | Browser GPU via WebGL |
| Infrastructure | Requires tile server | Only S3 / object storage |
| Band math | URL expression parameter | WebGL style expressions |
| Colormapping | Server-side (`colormap_name`) | Client-side (JS color scales) |
| Browser requirement | Any modern browser | WebGL-capable browser |
| Interactivity | New request per style change | Instant re-render |

### 📊 Data Catalog
Browse and discover available datasets through our comprehensive catalog:

**`https://api.explorer.eopf.copernicus.eu/browser/`**

### 📐 Data model update
The latest data model (processing baseline N0512+) simplifies band paths: resolution subgroups like `/r10m` are no longer needed. For example, `/measurements/reflectance:b04` replaces the former `/measurements/reflectance/r10m:b04`. Resolution levels are now handled natively by [Zarr multiscales conventions](https://github.com/zarr-conventions/multiscales).

<div style="height: 7rem"></div>

## Different date, different time <!--{ as="eox-map" class="overlay-br" mode="tour" }-->
Copernicus data 2025. <!--{ style="opacity: 0.75; font-size: 1rem;" }-->

### <!--{ layers='[{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2B_MSIL2A_20250804T103629_N0511_R008_T31TDH_20250804T130722/tiles/WebMercatorQuad/{z}/{x}/{y}.png?expression=(/measurements/reflectance/r10m:b08-/measurements/reflectance/r10m:b04)/(/measurements/reflectance/r10m:b08%2b/measurements/reflectance/r10m:b04)&rescale=-1,1&colormap_name=rdylgn"}}]' center=[2.88,43.05] zoom="12" }-->
#### Before Wildfires
NDVI from 20250804 over Southern France, before the devastating wildfires.
### <!--{ layers='[{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2A_MSIL2A_20250831T103701_N0511_R008_T31TDH_20250831T145420/tiles/WebMercatorQuad/{z}/{x}/{y}.png?expression=(/measurements/reflectance/r10m:b08-/measurements/reflectance/r10m:b04)/(/measurements/reflectance/r10m:b08%2b/measurements/reflectance/r10m:b04)&rescale=-1,1&colormap_name=rdylgn"}}]' center=[2.88,43.05] zoom="12" }-->
#### After Wildfires
NDVI from 20250819 over Southern France, after the devastating wildfires. We can see the burns scars.

### <!--{ layers='[{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2C_MSIL2A_20250811T112131_N0511_R037_T29TPF_20250811T152216/tiles/WebMercatorQuad/{z}/{x}/{y}.png?variables=/measurements/reflectance/r10m:b08&variables=/measurements/reflectance/r10m:b04&variables=/measurements/reflectance/r10m:b03&rescale=0,0.3"}}]' center=[-7,41] zoom="12" }-->
#### ... and band combinations of your choice

Here as false color IR (B08, B04, B03), in August 2025 over Northern Portugal

## Build your own interface using Zarr! <!-- { style="margin-top: 7rem" } -->

This story was built with `eox-storytelling` and `eox-map`
https://github.com/EOX-A/EOxElements

For a full-fledged EO dashboard interface that works with Zarr, use https://github.com/eodash/eodash
