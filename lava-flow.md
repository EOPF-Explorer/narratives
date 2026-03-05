# River of Fire: La Palma Visualized <!--{ as="img" mode="hero" src="https://www.esa.int/var/esa/storage/images/esa_multimedia/images/2021/10/new_lava_river_captured_by_copernicus_sentinel-2/23513241-1-eng-GB/New_lava_river_captured_by_Copernicus_Sentinel-2_pillars.jpg" }-->
#### Tracing the 85-day eruption of Cumbre Vieja through the eyes of Copernicus Sentinel-2, from the first explosion on September 19, 2021 to the silent aftermath in January 2022. <!--{ style="font-size:1rem;opacity:0.7;margin-top:1rem;" }-->

## The Eruption of Cumbre Vieja <!-- { style="margin-top: 7rem" } -->

On September 19, 2021, at 15:12 local time, the Cumbre Vieja volcanic ridge on the Spanish island of La Palma erupted after weeks of intensifying seismic activity. What followed was an 85-day geological crisis — the longest eruption on La Palma in recorded history — that did not end until December 13, 2021.

The eruption forced the evacuation of over 7,000 residents, destroyed approximately 3,000 buildings, and buried more than 1,200 hectares of land under lava. On September 28, the lava reached the Atlantic Ocean, creating a new coastal delta known as a *fajana* and releasing toxic plumes of hydrochloric acid and steam. Over the following weeks, multiple new vents opened, sending fresh lava flows in different directions and repeatedly threatening communities that had been considered safe.

Throughout it all, the Copernicus Sentinel-2 satellites provided a critical eye in the sky. Passing over La Palma every five days, they captured the eruption's evolution in wavelengths far beyond what the human eye can see. Let's follow the eruption through satellite imagery, stepping through time and beyond the visible spectrum.

<small>Source: [2021 Cumbre Vieja volcanic eruption — Wikipedia](https://en.wikipedia.org/wiki/2021_Cumbre_Vieja_volcanic_eruption)</small>

<div style="height: 7rem"></div>

## Seeing Through the Smoke <!--{ as="eox-map" class="overlay-br" mode="tour" }-->
Sentinel-2 Data, September 2021 – January 2022. <!--{ style="opacity: 0.75; font-size: 1rem;" }-->

### <!--{ layers='[{"type":"Tile","properties":{"id":"terrain-light","title":"Terrain Light"},"source":{"type":"XYZ","url":"https://s2maps-tiles.eu/wmts/1.0.0/terrain-light_3857/default/g/{z}/{y}/{x}.jpeg","projection":"EPSG:3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2B_MSIL2A_20210925T120319_N0500_R023_T28RBS_20230109T005655/tiles/WebMercatorQuad/{z}/{x}/{y}.png?variables=/measurements/reflectance:b04&variables=/measurements/reflectance:b03&variables=/measurements/reflectance:b02&rescale=0,0.25&color_formula=gamma rgb 1.3"}}]' center=[-17.87,28.61] zoom="12" animationOptions="{duration:500}" }-->
#### September 25 — Six Days In

This is the first clear Sentinel-2 acquisition after the eruption began. In *True Color* (using the Red, Green, and Blue bands), we can see the volcanic plume of smoke and ash streaming from the vent across the island. A dark scar of fresh lava has already begun spreading westward toward the coast.

But from true color alone, we can barely distinguish the active lava fronts from cooled rock. The smoke obscures much of the scene. To understand what's really happening, we need to look beyond visible light.

### <!--{ layers='[{"type":"Tile","properties":{"id":"terrain-light","title":"Terrain Light"},"source":{"type":"XYZ","url":"https://s2maps-tiles.eu/wmts/1.0.0/terrain-light_3857/default/g/{z}/{y}/{x}.jpeg","projection":"EPSG:3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2B_MSIL2A_20210925T120319_N0500_R023_T28RBS_20230109T005655/tiles/WebMercatorQuad/{z}/{x}/{y}.png?variables=/measurements/reflectance:b08&variables=/measurements/reflectance:b04&variables=/measurements/reflectance:b03&rescale=0,0.4&color_formula=gamma rgb 1.3"}}]' center=[-17.87,28.61] zoom="12" animationOptions="{duration:500}" }-->
#### Looking Beyond Visible Light

Our first step beyond the visible spectrum is a *False Color Infrared* composite, mapping Near-Infrared (B08 at 842 nm) to the red channel, and visible Red (B04) and Green (B03) to the remaining channels.

### <!--{ layers='[{"type":"Tile","properties":{"id":"terrain-light","title":"Terrain Light"},"source":{"type":"XYZ","url":"https://s2maps-tiles.eu/wmts/1.0.0/terrain-light_3857/default/g/{z}/{y}/{x}.jpeg","projection":"EPSG:3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2B_MSIL2A_20210925T120319_N0500_R023_T28RBS_20230109T005655/tiles/WebMercatorQuad/{z}/{x}/{y}.png?variables=/measurements/reflectance:b08&variables=/measurements/reflectance:b04&variables=/measurements/reflectance:b03&rescale=0,0.4&color_formula=gamma rgb 1.3"}}]' center=[-17.87,28.61] zoom="14" animationOptions="{duration:500}" }-->

Healthy vegetation reflects strongly in the near-infrared and appears bright red in this view. The lava-covered zone, by contrast, shows up as a stark dark scar — vegetation has been incinerated, and the bare rock absorbs NIR light. We can now clearly see the *extent* of the destruction, but we still can't see the *heat* of the active lava. For that, we need to go even deeper into the infrared.

### <!--{ layers='[{"type":"Tile","properties":{"id":"terrain-light","title":"Terrain Light"},"source":{"type":"XYZ","url":"https://s2maps-tiles.eu/wmts/1.0.0/terrain-light_3857/default/g/{z}/{y}/{x}.jpeg","projection":"EPSG:3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2B_MSIL2A_20210925T120319_N0500_R023_T28RBS_20230109T005655/tiles/WebMercatorQuad/{z}/{x}/{y}.png?variables=/measurements/reflectance:b12&variables=/measurements/reflectance:b11&variables=/measurements/reflectance:b04&rescale=0,0.6"}}]' center=[-17.87,28.61] zoom="14" animationOptions="{duration:500}" }-->
#### The River of Fire

Now we switch to *Short-Wave Infrared (SWIR)* bands — mapping B12 (~2190 nm) and B11 (~1610 nm) to the red and green channels. At these wavelengths, surfaces hotter than ~500°C begin to glow intensely.

The active lava flows now blaze in vivid orange and red. Temperatures exceeding 1000°C emit strongly at these wavelengths, while the smoke becomes semi-transparent. We can trace the incandescent channels flowing downhill toward the coast. This is the *"river of fire"* — invisible to our eyes but blazing in the infrared.

### <!--{ layers='[{"type":"Tile","properties":{"id":"terrain-light","title":"Terrain Light"},"source":{"type":"XYZ","url":"https://s2maps-tiles.eu/wmts/1.0.0/terrain-light_3857/default/g/{z}/{y}/{x}.jpeg","projection":"EPSG:3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2A_MSIL2A_20210930T120331_N0500_R023_T28RBS_20230109T180123/tiles/WebMercatorQuad/{z}/{x}/{y}.png?variables=/measurements/reflectance:b12&variables=/measurements/reflectance:b11&variables=/measurements/reflectance:b04&rescale=0,0.6"}}]' center=[-17.89,28.61] zoom="13" animationOptions="{duration:500}" }-->
#### September 30 — The Lava Meets the Sea

Five days later, the lava has reached the Atlantic Ocean the day before, on September 28th, creating a new lava delta — a *fajana*. Where molten rock meets seawater, violent steam explosions produce a dangerous plume of hydrochloric acid and fine glass particles known as *laze*.

The bright, glowing front at the coast marks the ocean entry point. The flow channel from vent to sea is now fully established — a river of fire several kilometers long. The SWIR composite makes it unmistakable.

### <!--{ layers='[{"type":"Tile","properties":{"id":"terrain-light","title":"Terrain Light"},"source":{"type":"XYZ","url":"https://s2maps-tiles.eu/wmts/1.0.0/terrain-light_3857/default/g/{z}/{y}/{x}.jpeg","projection":"EPSG:3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2A_MSIL2A_20211010T120331_N0500_R023_T28RBS_20230106T001906/tiles/WebMercatorQuad/{z}/{x}/{y}.png?variables=/measurements/reflectance:b12&variables=/measurements/reflectance:b11&variables=/measurements/reflectance:b04&rescale=0,0.6"}}]' center=[-17.87,28.61] zoom="13" animationOptions="{duration:500}" }-->
#### October 10 — A New Vent Opens

By mid-October, the eruption has intensified. A new vent has opened, sending a fresh lava flow in a slightly different direction. The bright SWIR signature reveals multiple active channels — the original flow continues feeding lava to the ocean, while a new branch threatens previously untouched areas to the north.

The volcanic system is far from settling down. For emergency responders on the ground, these satellite images were critical for planning evacuation routes and predicting which neighborhoods were at risk.

### <!--{ layers='[{"type":"Tile","properties":{"id":"terrain-light","title":"Terrain Light"},"source":{"type":"XYZ","url":"https://s2maps-tiles.eu/wmts/1.0.0/terrain-light_3857/default/g/{z}/{y}/{x}.jpeg","projection":"EPSG:3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2B_MSIL2A_20211015T120329_N0500_R023_T28RBS_20230104T221431/tiles/WebMercatorQuad/{z}/{x}/{y}.png?variables=/measurements/reflectance:b04&variables=/measurements/reflectance:b03&variables=/measurements/reflectance:b02&rescale=0,0.25&color_formula=gamma rgb 1.3"}}]' center=[-17.87,28.62] zoom="12" animationOptions="{duration:500}" }-->
#### October 15 — Under a Shroud of Ash

Five days later, a massive ash and smoke plume dominates the scene. In true color, the volcanic column stretches across the island, blanketing entire neighborhoods in grey ash. The scale of the plume gives a visceral sense of the eruption's ferocity — this is what residents on the ground were living through day after day.

On the ground, visibility dropped to near zero at times. Schools were closed, flights diverted, and air quality warnings were issued across the western Canary Islands.

### <!--{ layers='[{"type":"Tile","properties":{"id":"terrain-light","title":"Terrain Light"},"source":{"type":"XYZ","url":"https://s2maps-tiles.eu/wmts/1.0.0/terrain-light_3857/default/g/{z}/{y}/{x}.jpeg","projection":"EPSG:3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2B_MSIL2A_20211015T120329_N0500_R023_T28RBS_20230104T221431/tiles/WebMercatorQuad/{z}/{x}/{y}.png?variables=/measurements/reflectance:b12&variables=/measurements/reflectance:b11&variables=/measurements/reflectance:b04&rescale=0,0.6"}}]' center=[-17.88,28.63] zoom="14" animationOptions="{duration:500}" }-->
#### Seeing Through the Plume

Switching to SWIR, the smoke becomes partially transparent and the lava flows emerge once again. The active channels are still clearly glowing beneath the thick plume, confirming the eruption remains vigorous.

This demonstrates the critical operational value of SWIR imagery for emergency responders: even when visibility is zero on the ground and optical imagery shows only a blanket of grey, satellite infrared bands can still track active lava flows and identify new flow fronts in near real-time.

### <!--{ layers='[{"type":"Tile","properties":{"id":"terrain-light","title":"Terrain Light"},"source":{"type":"XYZ","url":"https://s2maps-tiles.eu/wmts/1.0.0/terrain-light_3857/default/g/{z}/{y}/{x}.jpeg","projection":"EPSG:3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2A_MSIL2A_20211030T120331_N0500_R023_T28RBS_20230105T031900/tiles/WebMercatorQuad/{z}/{x}/{y}.png?variables=/measurements/reflectance:b04&variables=/measurements/reflectance:b03&variables=/measurements/reflectance:b02&rescale=0,0.25&color_formula=gamma rgb 1.3"}}]' center=[-17.87,28.62] zoom="13" animationOptions="{duration:500}" }-->
#### October 30 — The Invisible Danger

By late October, the plume carries not just ash but dangerous concentrations of sulphur dioxide (SO₂). While Sentinel-2 cannot directly measure SO₂ — that is the domain of Sentinel-5P's TROPOMI instrument — the thick, persistent plume visible here hints at the toxic gases within.

SO₂ causes respiratory problems, damages crops, and produces acid rain, extending the eruption's impact far beyond the lava zone itself. Monitoring stations on the island recorded SO₂ levels well above safe thresholds, forcing additional evacuations in areas untouched by lava.

### <!--{ layers='[{"type":"Tile","properties":{"id":"terrain-light","title":"Terrain Light"},"source":{"type":"XYZ","url":"https://s2maps-tiles.eu/wmts/1.0.0/terrain-light_3857/default/g/{z}/{y}/{x}.jpeg","projection":"EPSG:3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2A_MSIL2A_20211030T120331_N0500_R023_T28RBS_20230105T031900/tiles/WebMercatorQuad/{z}/{x}/{y}.png?variables=/measurements/reflectance:b12&variables=/measurements/reflectance:b11&variables=/measurements/reflectance:b04&rescale=0,0.6"}}]' center=[-17.87,28.62] zoom="12" animationOptions="{duration:500}" }-->
#### Still Burning

Beneath the plume, the SWIR bands reveal that the lava flows continue unabated. The eruption is now in its sixth week with no sign of slowing down. The cumulative lava field has grown considerably since late September, covering agricultural land, roads, and entire neighborhoods under meters of solidified rock.

The contrast between the true-color and SWIR views of the same scene underscores a fundamental lesson: what you *can't* see in visible light can be just as important as what you can.

### <!--{ layers='[{"type":"Tile","properties":{"id":"terrain-light","title":"Terrain Light"},"source":{"type":"XYZ","url":"https://s2maps-tiles.eu/wmts/1.0.0/terrain-light_3857/default/g/{z}/{y}/{x}.jpeg","projection":"EPSG:3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2B_MSIL2A_20220103T120319_N0510_R023_T28RBS_20240423T015628/tiles/WebMercatorQuad/{z}/{x}/{y}.png?variables=/measurements/reflectance:b04&variables=/measurements/reflectance:b03&variables=/measurements/reflectance:b02&rescale=0,0.25&color_formula=gamma rgb 1.3"}}]' center=[-17.87,28.61] zoom="13" animationOptions="{duration:500}" }-->
#### January 3, 2022 — After the Fire

Three weeks after the eruption officially ended on December 13, the skies are finally clear. The full extent of the lava field is now visible in true color — a dark, barren scar cutting through what was once green farmland, banana plantations, and residential areas.

The new coastline, extended seaward by the lava delta, is clearly visible. Over 1,200 hectares of land lie buried. But quantifying the true extent of the damage from true color alone remains difficult — dark volcanic soil and dark lava look surprisingly similar.

### <!--{ layers='[{"type":"Tile","properties":{"id":"terrain-light","title":"Terrain Light"},"source":{"type":"XYZ","url":"https://s2maps-tiles.eu/wmts/1.0.0/terrain-light_3857/default/g/{z}/{y}/{x}.jpeg","projection":"EPSG:3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2B_MSIL2A_20220103T120319_N0510_R023_T28RBS_20240423T015628/tiles/WebMercatorQuad/{z}/{x}/{y}.png?variables=/measurements/reflectance:b12&variables=/measurements/reflectance:b11&variables=/measurements/reflectance:b04&rescale=0,0.6"}}]' center=[-17.87,28.61] zoom="13" animationOptions="{duration:500}" }-->
#### Cooling Down

In SWIR, the lava field appears uniformly dark — no more glowing channels, no more incandescent vents. The eruption is truly over. Compare this to the blazing rivers we saw in September and October: the silence is striking.

But to map the affected area precisely and distinguish it from the surrounding dark volcanic terrain, we need one more tool — a spectral index.

### <!--{ layers='[{"type":"Tile","properties":{"id":"terrain-light","title":"Terrain Light"},"source":{"type":"XYZ","url":"https://s2maps-tiles.eu/wmts/1.0.0/terrain-light_3857/default/g/{z}/{y}/{x}.jpeg","projection":"EPSG:3857"}},{"type":"Tile","properties":{"id":"s-2-l2a-nbr"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2B_MSIL2A_20220103T120319_N0510_R023_T28RBS_20240423T015628/tiles/WebMercatorQuad/{z}/{x}/{y}.png?expression=(/measurements/reflectance:b08-/measurements/reflectance:b12)/(/measurements/reflectance:b08%2b/measurements/reflectance:b12)&rescale=-1,1&colormap_name=rdbu"}}]' center=[-17.87,28.61] zoom="13" animationOptions="{duration:500}" }-->
#### Measuring the Scar: Normalized Burn Ratio

The *Normalized Burn Ratio* (NBR) exploits the contrast between Near-Infrared (B08, strongly reflected by healthy vegetation) and SWIR (B12, sensitive to bare and burned surfaces):

```
NBR = (B08 − B12) / (B08 + B12)
```

Values range from −1 to +1. Healthy, vegetated areas appear in **blue** (high NBR), while the lava-covered zone stands out as a stark **red** area (low or negative NBR). The boundary between affected and unaffected land is immediately apparent.

The total area of the lava field — approximately 1,200 hectares — is laid bare in a single index. What took weeks of ground surveys can be seen at a glance from space.

## The Formula for Fire <!-- { style="margin-top: 7rem" } -->

Throughout this story, we used three different visualization techniques to see what's invisible to the naked eye. Each reveals a different aspect of the eruption:

### False Color Infrared (B08, B04, B03)

By mapping the *Near-Infrared* band (B08 at 842 nm) to the red display channel, we leverage the fact that healthy vegetation reflects NIR light very strongly. In this composite, living plants glow bright red while bare rock, lava, and ash appear dark. This makes it ideal for mapping the *extent of destruction* — where vegetation has been incinerated or buried.

### SWIR Composite (B12, B11, B04)

The *Short-Wave Infrared* composite maps B12 (~2190 nm) and B11 (~1610 nm) to the red and green channels. At these wavelengths:

*   **Hot surfaces glow** — lava above ~500°C emits strongly, making active flows appear as vivid orange and red channels.
*   **Smoke becomes transparent** — SWIR wavelengths penetrate ash and smoke plumes that completely obscure the view in visible light.
*   **Background context** — B04 (visible red) in the blue channel provides familiar geographic context for cooler areas.

The combination `(B12, B11, B04)` is a standard "Atmospheric Penetration" composite, widely used for fire and volcanic monitoring.

### Normalized Burn Ratio: (B08 − B12) / (B08 + B12)

The *NBR* is a single-value spectral index that quantifies the severity of surface change. Healthy vegetation has high B08 (NIR) reflectance and low B12 (SWIR) reflectance, yielding a high positive NBR. Bare lava and burned ground show the opposite pattern, producing low or negative values. Displayed with a **red-blue** colormap, the affected area becomes immediately and precisely distinguishable from the surrounding landscape.

## Here's how we built this <!-- { style="margin-top: 7rem" } -->

The full story narrative is available open source [here](https://github.com/EOPF-Explorer/narratives/blob/main/lava-flow.md).

This interactive story is powered by [software and services](/software-services) of EOPF Explorer:

### 🌐 TiTiler

The dynamic tile serving, band combination, and index computation is handled by **[TiTiler](https://github.com/EOPF-Explorer/titiler-eopf)**. It allows us to access the raw Zarr data from the Copernicus archive and render RGB composites, false-color visualizations, and computed spectral indices on-the-fly — without pre-generating images. Learn how to build your own visualizations in the **[TiTiler integration guide](/software-services/titiler)**.

### 📊 EOxElements & eodash

The interface you are using is built with **[EOxElements](https://github.com/EOX-A/EOxElements)** (specifically `eox-storytelling` and `eox-map`). Learn how to create your own story in the **[EOxElements integration guide](/software-services/eoxelements)**

