# Plan: Update NDVI Story First Section

**TL;DR** — Update the first half of ndvi.md (sections "See the health of plants from space", "Sentinel Bands" tour, and "Here's how we built this") to use the new item `S2B_MSIL2A_20260225T095029_N0512_R079_T33TVF_20260225T141422` with the updated data model (no resolution subgroups), and present both server-side (titiler) and client-side (GeoZarr/OpenLayers WebGL) NDVI rendering with explicit comparison of pros/cons.

## Steps

### 1. Update the "Sentinel Bands" tour

Update the tour in ndvi.md from 2 steps to 3 steps, all using the new item:

#### Step 1 — "The world in colors" (true color RGB, titiler)

Keep the educational text about light/photosynthesis. Replace the layer JSON to use the new item with updated variable paths (`/measurements/reflectance:b04`, `:b03`, `:b02` — no `r10m`). Keep `center=[14.2,40.8]`, same tile `T33TVF`. Source type stays `XYZ` / `Tile`.

#### Step 2 — "Server-side NDVI with TiTiler" (titiler rendered NDVI)

Replace the current NDVI step. Update the expression URL to use new paths: `(/measurements/reflectance:b08-/measurements/reflectance:b04)/(/measurements/reflectance:b08%2b/measurements/reflectance:b04)`. Keep `colormap_name=rdylgn`, `rescale=-1,1`. The text should explain that this is **server-side rendering** — the API computes NDVI and returns pre-rendered PNG tiles. Mention that `b08` (10m, 842nm) is used as the NIR band.

#### Step 3 — "Client-side NDVI with GeoZarr" (new, WebGL rendered NDVI)

Add a new tour step using `"type": "WebGLTile"` with `"source.type": "GeoZarr"`, following the pattern from cloud-native-eo.md. The source URL will be `https://s3.explorer.eopf.copernicus.eu/esa-zarr-sentinel-explorer-fra/tests-output/sentinel-2-l2a/S2B_MSIL2A_20260225T095029_N0512_R079_T33TVF_20260225T141422.zarr`, group `measurements/reflectance`, bands `["b04", "b8a"]`. The `style` block will include an NDVI WebGL expression computing `(band2 - band1) / (band2 + band1)` mapped to a green color ramp, following the pattern from the OpenLayers NDVI tutorial. The text should explain **client-side rendering** — raw Zarr chunks stream to the browser and WebGL computes NDVI on the GPU. Mention that `b8a` (20m, 865nm narrow-band NIR) is used here, and explain briefly why (`b8a` is in the same resolution group as other 20m bands, better spectral definition; `b08` has 10m resolution but broader wavelength).

### 2. Rewrite the "Here's how we built this" section

Cover both approaches:

#### Intro paragraph

Explain that this story demonstrates two complementary ways to visualize NDVI from Zarr data — server-side and client-side — each with distinct trade-offs.

#### Server-side rendering (TiTiler) subsection

- Describe `titiler-eopf` as before — open-source tile server, simple HTTP endpoints
- Live API: `https://api.explorer.eopf.copernicus.eu/raster/`
- Highlight: no WebGL required, works everywhere, server handles computation and colormapping, but requires server infrastructure and each tile is a round-trip
- Update the dynamic processing link to use the new item and new paths

#### Client-side rendering (GeoZarr + OpenLayers) subsection

- Describe the GeoZarr approach: raw data streamed directly from object storage (S3) to the browser, rendered using OpenLayers' `WebGLTile` layer with the `GeoZarr` source
- Zarr store URL pattern: `https://s3.explorer.eopf.copernicus.eu/esa-zarr-sentinel-explorer-fra/tests-output/sentinel-2-l2a/{ITEM_ID}.zarr`
- Highlight: no server infrastructure needed beyond S3, computation happens on the GPU, fully interactive styling, but requires WebGL support and transfers raw data
- Mention that the STAC API provides the Zarr store URL via the `store` link relation (as shown in cloud-native-eo.md)
- Link to the OpenLayers NDVI tutorial for a deeper interactive example with adjustable color scales

#### Comparison table

| Aspect | Server-side (TiTiler) | Client-side (GeoZarr) |
|---|---|---|
| Rendering | Server computes & returns PNG tiles | Browser GPU via WebGL |
| Infrastructure | Requires tile server | Only S3 / object storage |
| Band math | URL expression parameter | WebGL style expressions |
| Colormapping | Server-side (`colormap_name`) | Client-side (JS color scales) |
| Browser requirement | Any modern browser | WebGL-capable browser |
| Interactivity | New request per style change | Instant re-render |

#### Data Catalog

Keep the existing `https://api.explorer.eopf.copernicus.eu/browser/` reference.

#### Data model note

Briefly mention that the new data model (N0512+) simplifies band paths — no more resolution subgroups (e.g., `/measurements/reflectance:b04` instead of `/measurements/reflectance/r10m:b04`), as resolution levels are now handled by Zarr multiscales conventions.

### 3. Update the NDVI formula text

In step 2 of the tour: keep the formula explanation as-is (it's band-agnostic), but after the formula add a brief note that Sentinel-2 offers two NIR bands — `B08` (10m) and `B8A` (20m) — and both are valid for NDVI, used by each approach respectively.

## Verification

- Render ndvi.md in an `eox-storytelling` environment. Verify that:
  - Tour step 1 shows true color RGB of the new item over Naples
  - Tour step 2 renders NDVI via titiler (server-side PNG tiles)
  - Tour step 3 renders NDVI via GeoZarr (client-side WebGL)
  - Scrolling transitions smoothly between all 3 steps
- Confirm the titiler tile URL resolves: `https://api.explorer.eopf.copernicus.eu/raster/collections/sentinel-2-l2a/items/S2B_MSIL2A_20260225T095029_N0512_R079_T33TVF_20260225T141422/tiles/WebMercatorQuad/12/2192/1497.png?variables=/measurements/reflectance:b04&variables=/measurements/reflectance:b03&variables=/measurements/reflectance:b02&rescale=0,1`
- Confirm the Zarr store URL resolves: `https://s3.explorer.eopf.copernicus.eu/esa-zarr-sentinel-explorer-fra/tests-output/sentinel-2-l2a/S2B_MSIL2A_20260225T095029_N0512_R079_T33TVF_20260225T141422.zarr`
- Verify all links in the "Here's how we built this" section resolve

## Decisions

- **b8a for client-side, b08 for server-side**: Matches each tool's existing tutorials and highlights a real-world choice users face (resolution vs spectral precision)
- **3-step tour**: RGB → Server NDVI → Client NDVI keeps narrative flow educational without overwhelming with 4 steps
- **New variable paths**: `/measurements/reflectance:b04` (no `r10m`) per the updated data model (N0512+, multiscales conventions)
- **Scope**: Only the first half of the file (intro, first tour, "built this") is touched; the second tour ("Different date, different time") and outro are left for a subsequent update
