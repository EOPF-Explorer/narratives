# Unveiling the Green: Visualizing NDVI from Zarr <!--{ as="img" mode="hero" src="https://custom-scripts.sentinel-hub.com/custom-scripts/sentinel-2/ndvi/fig/fig1.png" }-->
#### Showing the classical NDVI example powered by the Zarr file format. Scroll down to get started! <!--{ style="font-size:1rem;opacity:0.7;margin-top:1rem;" }-->

## See the health of plants from space <!-- { style="margin-top: 7rem" } -->

Have you ever wondered how we can see the health of plants from space? It's not magic, it's science! Plants, like all living things, interact with light in unique ways. By observing these interactions, especially with satellites orbiting our planet, we can unlock a wealth of information about vegetation health, growth, and even drought stress.

This is where the Normalized Difference Vegetation Index, or NDVI, comes into play. It's a simple yet powerful tool used by scientists, farmers, and environmentalists worldwide to monitor plant vigor.

<div style="height: 7rem"></div>

## Sentinel Bands <!--{ as="eox-map" class="overlay-br" mode="tour" }-->
Copernicus data 2025. <!--{ style="opacity: 0.75; font-size: 1rem;" }-->

### <!--{ layers='[{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2C_MSIL2A_20250913T095041_N0511_R079_T33TVF_20250913T151113/tiles/WebMercatorQuad/{z}/{x}/{y}.png?variables=/measurements/reflectance/r10m:b04&variables=/measurements/reflectance/r10m:b03&variables=/measurements/reflectance/r10m:b02&rescale=0,0.3"}},{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}}]' center=[14.2,40.8] zoom="12" animationOptions="{duration:500}" }-->
#### The world in colors
To understand NDVI, we first need to talk about light. We see the world in colors like red, green, and blue – this is called the visible spectrum. But there's more to light than meets the eye. Plants, for instance, have a very distinct relationship with red light and near-infrared (NIR) light.

Think of a healthy plant: it absorbs most of the red light from the sun for photosynthesis, using that energy to grow. But it strongly reflects near-infrared light. It's almost like a plant's way of saying, "I'm busy photosynthesizing, here's some NIR light back!"

Conversely, unhealthy or sparse vegetation will absorb less red light and reflect less NIR light. It's this contrast between absorbed red and reflected NIR that forms the basis of NDVI.

### <!--{ layers='[{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2C_MSIL2A_20250913T095041_N0511_R079_T33TVF_20250913T151113/tiles/WebMercatorQuad/{z}/{x}/{y}.png?expression=(/measurements/reflectance/r10m:b08-/measurements/reflectance/r10m:b04)/(/measurements/reflectance/r10m:b08%2b/measurements/reflectance/r10m:b04)&rescale=-1,1&colormap_name=rdylgn"}},{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}}]' center=[14.2,40.8] zoom="12" animationOptions="{duration:500}" }-->
#### The Normalized difference vegetation index
For our NDVI calculation, we'll focus on two key bands from Sentinel-2:
**Band 4 (B04): Red light** and **Band 8 (B08): Near-Infrared (NIR) light**

Calculating NDVI is surprisingly straightforward. It's a simple ratio that helps us quantify the difference between NIR and Red reflectance. The formula looks like this:

**NDVI = (NIR - Red) / (NIR + Red)**

Or, using our Sentinel-2 bands:

**NDVI = (B08 - B04) / (B08 + B04)**

## Here's how we built this <!-- { style="margin-top: 7rem" } -->
This demo uses the endpoints [...]
Date: 20250913, location: Naples

![](https://placehold.co/400x300?text=Some+image+here)

On the fly rendering [...] - what you're seeing is dynamically rendered NDVI, no preproccing needed, it works for any date and location in the archive without prior processing [...]

<div style="height: 7rem"></div>

## Different date, different time <!--{ as="eox-map" class="overlay-br" mode="tour" }-->
Copernicus data 2025. <!--{ style="opacity: 0.75; font-size: 1rem;" }-->

### <!--{ layers='[{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2B_MSIL2A_20250804T103629_N0511_R008_T31TDH_20250804T130722/tiles/WebMercatorQuad/{z}/{x}/{y}.png?expression=(/measurements/reflectance/r10m:b08-/measurements/reflectance/r10m:b04)/(/measurements/reflectance/r10m:b08%2b/measurements/reflectance/r10m:b04)&rescale=-1,1&colormap_name=rdylgn"}},{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}}]' center=[2.88,42.8] zoom="12" }-->
#### Works for any location...
Same expression, but 20250804 over Southern France

### <!--{ layers='[{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2C_MSIL2A_20250811T112131_N0511_R037_T29TPF_20250811T152216/tiles/WebMercatorQuad/{z}/{x}/{y}.png?variables=/measurements/reflectance/r10m:b08&variables=/measurements/reflectance/r10m:b04&variables=/measurements/reflectance/r10m:b03&rescale=0,0.3"}},{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}}]' center=[-7,41] zoom="12" }-->
#### ... and band combinations of your choice
Here as false color IR (B08, B04, B03), 20250811 over Northern Portugal

## Build your own interface using Zarr! <!-- { style="margin-top: 7rem" } -->
Reference/links to API

This story was built with `eox-storytelling` and `eox-map`
https://github.com/EOX-A/EOxElements

For a full-fledged EO dashboard interface that works with Zarr, use https://github.com/eodash/eodash

More closing text here possibly.
