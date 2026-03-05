## Plan: Rewrite Lava Flow Narrative with Eruption Timeline

**TL;DR** — Completely rewrite [lava-flow.md](narratives/lava-flow.md) to transform the existing 2-step static narrative into a rich chronological story of the 2021 Cumbre Vieja eruption. The single map tour will expand from 2 steps to ~13 steps, covering 6 Sentinel-2 acquisition dates (Sep 25 → Jan 3), with a pedagogical band-transition on the first date (True Color → False Color IR → SWIR), temporal progression through the eruption's key moments, and a final NBR burn-severity index to quantify the damage. All tile URLs follow the existing TiTiler API pattern from the workspace conventions.

**Steps**

1. **Update the hero section** ([lava-flow.md](narratives/lava-flow.md#L1-L2)). Keep the existing hero image URL and title "River of Fire: La Palma Visualized". Update the subtitle to mention the full timeline: *"Tracing the 85-day eruption of Cumbre Vieja through the eyes of Copernicus Sentinel-2, from the first explosion on September 19, 2021 to the silent aftermath in January 2022."*

2. **Expand the introduction section** ([lava-flow.md](narratives/lava-flow.md#L4-L11)). Rewrite the "The Eruption of Cumbre Vieja" prose to set the full scene:
   - The eruption began September 19, 2021, at 15:12 local time
   - It lasted 85 days, ending December 13, 2021
   - Over 7,000 people evacuated, ~3,000 buildings destroyed, ~1,200 hectares covered by lava
   - Lava reached the ocean on September 28, creating a new delta (fajana)
   - Multiple vents opened over the course of the eruption
   - Reference the [Wikipedia article](https://en.wikipedia.org/wiki/2021_Cumbre_Vieja_volcanic_eruption) as a source
   - Introduce the narrative premise: *"Let's follow the eruption through satellite imagery, stepping through time and beyond the visible spectrum."*

3. **Restructure the map tour** — Replace the existing 2-step tour at [lava-flow.md](narratives/lava-flow.md#L13-L30) with a single expanded tour containing ~13 steps across 6 dates. The `##` tour header remains `as="eox-map" class="overlay-br" mode="tour"`. Update the caption to: *"Sentinel-2 Data, September 2021 – January 2022."*

4. **Tour Step 1 — Sep 25: True Color (First Look)** — New step using item `S2B_MSIL2A_20210925T120319_N0500_R023_T28RBS_20230109T005655` with True Color bands (B04, B03, B02), `rescale=0,0.25`, `color_formula=gamma rgb 1.3`, center `[-17.87, 28.61]`, zoom `12`. Title: *"Six Days In"*. Prose: the eruption began 6 days ago, this is the first clear Sentinel-2 pass. Smoke and ash are visible, and a dark scar of fresh lava has already begun spreading westward. But from true color alone, we can barely distinguish the active fronts.

5. **Tour Step 2 — Sep 25: False Color IR (Intermediate)** — Same item, switch to False Color IR bands (B08, B04, B03), `rescale=0,0.4`, `color_formula=gamma rgb 1.3`, same center/zoom. Title: *"Looking Beyond Visible Light"*. Prose: explain that B08 (Near-Infrared at 842nm) is strongly reflected by vegetation. Healthy vegetation appears bright red; the lava-covered zone appears as a stark dark scar. We can now clearly see the *extent* of the destruction — but we still can't see the *heat* of the active lava. For that, we need to go even deeper into the infrared.

6. **Tour Step 3 — Sep 25: SWIR (Revealing the Fire)** — Same item, SWIR composite (B12, B11, B04), `rescale=0,0.6`, same center/zoom. Title: *"The River of Fire"*. Prose: switching to Short-Wave Infrared bands, the active lava flows now glow vivid orange and red. Temperatures exceeding 1000°C emit strongly at these wavelengths. The smoke becomes semi-transparent, and we can trace the incandescent channels flowing downhill toward the coast. This is the *"river of fire"* — invisible to our eyes but blazing in the infrared.

7. **Tour Step 4 — Sep 30: SWIR (Lava Reaches the Ocean)** — New item `S2A_MSIL2A_20210930T120331_N0500_R023_T28RBS_20230109T180123`, SWIR composite (B12, B11, B04), `rescale=0,0.6`, center `[-17.89, 28.61]`, zoom `13`. Title: *"The Lava Meets the Sea"*. Prose: five days later, the lava has reached the Atlantic Ocean, creating a new lava delta (fajana). Where molten rock meets seawater, violent steam explosions create a dangerous plume of hydrochloric acid and glass particles known as *laze*. The bright glowing front at the coast marks the entry point. The flow channel from vent to ocean is now fully established — a river of fire several kilometers long.

8. **Tour Step 5 — Oct 10: SWIR (New Vent)** — Existing item `S2A_MSIL2A_20211010T120331_N0500_R023_T28RBS_20230106T001906`, SWIR composite (B12, B11, B04), `rescale=0,0.6`, center `[-17.87, 28.61]`, zoom `13`. Title: *"A New Vent Opens"*. Prose: by mid-October, the eruption has intensified. A new vent has opened, sending a fresh lava flow in a slightly different direction. The bright SWIR signature reveals multiple active channels now. The original flow continues, while the new branch threatens previously untouched areas. The volcanic system is far from settling down.

9. **Tour Step 6 — Oct 15: True Color (Smoke Plume)** — New item `S2B_MSIL2A_20211015T120329_N0500_R023_T28RBS_20230104T221431`, True Color bands (B04, B03, B02), `rescale=0,0.25`, `color_formula=gamma rgb 1.3`, center `[-17.87, 28.62]`, zoom `12`. Title: *"Under a Shroud of Ash"*. Prose: five days later, a massive ash and smoke plume dominates the scene. In true color, the volcanic column stretches across the island, blanketing entire neighborhoods in ash. The scale of the plume gives a sense of the eruption's ferocity — this is what residents on the ground were living through.

10. **Tour Step 7 — Oct 15: SWIR (Lava Under Smoke)** — Same item, SWIR composite (B12, B11, B04), `rescale=0,0.6`, same center/zoom. Title: *"Seeing Through the Plume"*. Prose: switching to SWIR, the smoke becomes partially transparent and the lava flows emerge once again. The active channels are still clearly glowing, confirming the eruption remains vigorous. This demonstrates the critical operational value of SWIR imagery for emergency responders — even when visibility is zero on the ground, satellites can track the lava.

11. **Tour Step 8 — Oct 30: True Color (SO₂ Hazard)** — New item `S2A_MSIL2A_20211030T120331_N0500_R023_T28RBS_20230105T031900`, True Color bands (B04, B03, B02), `rescale=0,0.25`, `color_formula=gamma rgb 1.3`, center `[-17.87, 28.62]`, zoom `12`. Title: *"The Invisible Danger"*. Prose: by late October, the plume carries not just ash but dangerous concentrations of sulphur dioxide (SO₂). While Sentinel-2 cannot directly measure SO₂ (that's the domain of Sentinel-5P's TROPOMI), the visible plume hints at the toxic gases within. SO₂ causes respiratory problems and acid rain, extending the eruption's impact far beyond the lava zone.

12. **Tour Step 9 — Oct 30: SWIR** — Same item, SWIR composite (B12, B11, B04), `rescale=0,0.6`, same center/zoom. Title: *"Still Burning"*. Prose: beneath the plume, the SWIR bands reveal the lava flows continue. The eruption is now in its sixth week with no sign of abating. The cumulative lava field has grown considerably, covering agricultural land, roads, and entire neighborhoods.

13. **Tour Step 10 — Jan 3 2022: True Color (Aftermath)** — New item `S2B_MSIL2A_20220103T120319_N0510_R023_T28RBS_20240423T015628`, True Color bands (B04, B03, B02), `rescale=0,0.25`, `color_formula=gamma rgb 1.3`, center `[-17.87, 28.61]`, zoom `13`. Title: *"After the Fire"*. Prose: three weeks after the eruption officially ended on December 13, the skies are finally clear. The full extent of the lava field is now visible — a dark, barren scar cutting through what was once green farmland and residential areas. The new coastline, extended by the lava delta, is clearly visible. But the true extent of the damage is hard to quantify from true color alone.

14. **Tour Step 11 — Jan 3 2022: SWIR (Cooled lava)** — Same item, SWIR composite (B12, B11, B04), `rescale=0,0.6`, same center/zoom. Title: *"Cooling Down"*. Prose: in SWIR, the lava field appears uniformly dark — no more glowing channels, no more incandescent vents. The eruption is truly over. But to quantify the damage to the landscape, we need one more tool.

15. **Tour Step 12 — Jan 3 2022: NBR Index** — Same item, using the `expression=` parameter to compute NBR: `(/measurements/reflectance/r10m:b08-/measurements/reflectance/r20m:b12)/(/measurements/reflectance/r10m:b08%2b/measurements/reflectance/r20m:b12)` with `rescale=-1,1` and `colormap_name=rdbu`. Same center/zoom. Title: *"Measuring the Scar: Normalized Burn Ratio"*. Prose: the Normalized Burn Ratio (NBR) uses the contrast between Near-Infrared (B08, reflected by vegetation) and SWIR (B12, sensitive to burned/bare surfaces). The formula `(B08 − B12) / (B08 + B12)` produces values from −1 to +1. Healthy vegetation is blue (high NBR), while the lava-covered area appears as a stark red zone (low/negative NBR). The total affected area is immediately apparent — approximately 1,200 hectares of land transformed forever.

16. **Update "The Formula for Fire" section** ([lava-flow.md](narratives/lava-flow.md#L32-L42)). Expand to cover all three visualization techniques used:
    - **False Color IR (B08, B04, B03)** — NIR highlights vegetation; destroyed areas appear dark
    - **SWIR Composite (B12, B11, B04)** — penetrates smoke, reveals heat from active lava
    - **NBR Index: (B08 − B12) / (B08 + B12)** — quantifies burn/lava severity on a −1 to +1 scale
    - Briefly explain why each is useful in the context of volcanic monitoring

17. **Rename "Technology Stack" to "How did we build this?"** ([lava-flow.md](narratives/lava-flow.md#L44-L53)), matching the convention used in ndci.md. Update the TiTiler description to link to the integration how-to at [/software-services/titiler/rgb](https://explorer.eopf.copernicus.eu/software-services/titiler/rgb). Consider adding a mention of Sentinel-5P/TROPOMI for SO₂ monitoring as a cross-reference.

**Verification**
- Render the narrative in the eox-storytelling viewer and confirm all 12 tour steps load tiles correctly
- Verify each item ID returns valid tiles by testing a single tile URL in a browser, e.g.: `https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2B_MSIL2A_20210925T120319_N0500_R023_T28RBS_20230109T005655/tiles/WebMercatorQuad/13/3989/3284.png?variables=/measurements/reflectance/r10m:b04&variables=/measurements/reflectance/r10m:b03&variables=/measurements/reflectance/r10m:b02&rescale=0,0.25`
- Verify the NBR expression URL renders correctly with `colormap_name=rdbu`
- Check that center/zoom values frame the lava field properly for each date (the lava field expands over time; some steps may need slight center adjustments)
- Validate markdown structure: `##` for tour declaration, `###` for step configs, `####` for step titles

**Decisions**
- **Intermediate step**: False Color IR (B08, B04, B03) — shows vegetation destruction before revealing heat via SWIR
- **Tour layout**: Single long tour with ~12 steps — keeps the fluid map experience
- **NBR colormap**: `rdbu` — red for burned/lava (low NBR), blue for healthy (high NBR)
- **SO₂ visualization**: True Color (visible plume) + SWIR (lava beneath) combo with textual explanation that SO₂ detection requires Sentinel-5P
- **NBR band resolution mismatch**: B08 is 10m, B12 is 20m — TiTiler handles the resampling internally when using the `expression=` parameter with mixed resolution paths
