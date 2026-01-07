# River of Fire: La Palma Visualized <!--{ as="img" mode="hero" src="https://www.esa.int/var/esa/storage/images/esa_multimedia/images/2021/10/new_lava_river_captured_by_copernicus_sentinel-2/23513241-1-eng-GB/New_lava_river_captured_by_Copernicus_Sentinel-2_pillars.jpg" }-->
#### Witnessing the 2021 Cumbre Vieja eruption through the eyes of Sentinel-2 satellites. <!--{ style="font-size:1rem;opacity:0.7;margin-top:1rem;" }-->

## The Eruption of Cumbre Vieja <!-- { style="margin-top: 7rem" } -->

In September 2021, the Cumbre Vieja volcano on the Spanish island of La Palma erupted, initiating a months-long geological event that reshaped the island's landscape. The eruption, which lasted for 85 days, ejected millions of cubic meters of lava and ash, destroying thousands of buildings and forcing widespread evacuations.

While the eruption was a devastating natural disaster, satellite imagery played a crucial role in monitoring the flow of lava and assessing the damage in real-time. By observing the volcano from space, scientists and emergency responders could track the active lava fronts and predict their path.

<div style="height: 7rem"></div>

## Seeing Through the Smoke <!--{ as="eox-map" class="overlay-br" mode="tour" }-->
Sentinel-2 Data, October 10, 2021. <!--{ style="opacity: 0.75; font-size: 1rem;" }-->

### <!--{ layers='[{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2C_MSIL2A_20250913T095041_N0511_R079_T33TVF_20250913T151113/tiles/WebMercatorQuad/{z}/{x}/{y}.png?variables=/measurements/reflectance/r10m:b04&variables=/measurements/reflectance/r10m:b03&variables=/measurements/reflectance/r10m:b02&rescale=0,0.25&color_formula=gamma rgb 1.3"}}]' center=[14.2,40.8] zoom="12" animationOptions="{duration:500}" }-->
#### True Color View
*(Note: Visualizing 2025 Data from Vesuvius as a placeholder for unavailable La Palma 2021 data)*

In the *True Color* rendering (using Red, Green, and Blue bands), the volcano's plume of smoke and ash is the most prominent feature. While we can see the path of destruction, the active lava flows are often obscured by the smoke or simply appear as dark rock.

This view mimics what the human eye would see from space, but it misses the intense heat radiating from the ground. To see the "river of fire", we need to look beyond the visible spectrum.

### <!--{ layers='[{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2C_MSIL2A_20250913T095041_N0511_R079_T33TVF_20250913T151113/tiles/WebMercatorQuad/{z}/{x}/{y}.png?variables=/measurements/reflectance/r20m:b12&variables=/measurements/reflectance/r20m:b11&variables=/measurements/reflectance/r10m:b04&rescale=0,0.6"}}]' center=[14.2,40.8] zoom="12" animationOptions="{duration:500}" }-->
#### Unveiling the Lava (SWIR)
*(Note: Visualizing 2025 Data from Vesuvius as a placeholder for unavailable La Palma [-17.85,28.61] 2021 data)*

By switching to *Short-Wave Infrared (SWIR)* bands, the scene changes dramatically. The hot lava, reaching temperatures over 1000°C, emits intense radiation in the SWIR part of the spectrum.

In this visualization, the active lava flows glow in bright orange and red, while the smoke becomes semi-transparent. This allows us to clearly identify the location of the active vents and the main lava channel flowing towards the ocean. It even highlights cooling lava flows that are still hot but not emitting visible light.

## The Formula for Fire <!-- { style="margin-top: 7rem" } -->

To create the "Lava Flow" visualization above, we use a specific combination of Sentinel-2 bands that are sensitive to both heat and ground composition.

We map these satellite bands to the Red, Green, and Blue channels of the display:

*   **RED Channel: Band 12 (SWIR 2)** - Centered at ~2190 nm. This band is highly sensitive to very hot surfaces like active lava.
*   **GREEN Channel: Band 11 (SWIR 1)** - Centered at ~1610 nm. Also sensitive to heat and differences in moisture/vegetation structure.
*   **BLUE Channel: Band 04 (Red)** - Centered at ~665 nm. Provides context for the background and cooler areas.

The combination `(B12, B11, B04)` is a standard "Atmospheric Penetration" or "False Color Urban/Fire" composite. The incredibly bright signal from the lava in B12 and B11 makes it stand out vividly against the background.

## Technology Stack <!-- { style="margin-top: 7rem" } -->

This interactive story is powered by modern Earth Observation technologies:

### 🌐 TiTiler
The dynamic tile serving and band combination is handled by **[TiTiler](https://developmentseed.org/titiler/)** (specifically `titiler-eopf`). It allows us to access the raw Zarr data from the Copernicus archive and render these visualizations on-the-fly without pre-generating images.

### 📊 EOxElements & eodash
The interface you are using is built with **[EOxElements](https://github.com/EOX-A/EOxElements)** (specifically `eox-storytelling` and `eox-map`). For a more complex dashboard experience to explore this data further, check out **[eodash](https://eodash.eox.at/)**.
