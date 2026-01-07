# Monitoring Cyanobacteria in Venice Lagoon <!--{ as="img" mode="hero" src="https://github.com/EOPF-Explorer/narratives/blob/ndci/chl-ndci/hero.png?raw=true" }-->

#### Real-time chlorophyll-a detection using the Normalised Difference Chlorophyll Index and satellite data <!--{ style="font-size:1rem;opacity:0.7;margin-top:1rem;" }-->

## A unique ecosystem under pressure <!-- { style="margin-top: 7rem" } -->

Venice Lagoon represents one of Europe's most remarkable coastal ecosystems – a delicate balance between land and sea that has supported human civilization for over a millennium. But this shallow, enclosed water body faces mounting environmental pressures that threaten both its ecological health and the communities that depend on it.

Among these challenges, the proliferation of cyanobacteria – commonly known as blue-green algae – has become increasingly problematic. These microscopic organisms, while natural components of aquatic ecosystems, can multiply rapidly under certain conditions, creating harmful algal blooms that disrupt marine life, impact water quality, and affect local economies.

<div style="height: 7rem"></div>

## Do you recognize this place? <!--{ as="eox-map" class="overlay-br" mode="tour" }-->

Copernicus data 2025. <!--{ style="opacity: 0.75; font-size: 1rem;" }-->

### <!--{ layers='[{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}}]' center=[12.8,45.5] zoom=10.5 animationOptions="{duration:500}" }-->

#### Northern Italy from Space

This distinctive lagoon system along Italy's Adriatic coast is instantly recognizable from above. The intricate pattern of islands, channels, and shallow waters creates a unique fingerprint visible from space.

<small>Image: Copernicus Sentinel-2 data 2022 cloudless, processed by EOX IT GmbH</small>

### <!--{ layers='[{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/openeo/services/xyz/25107b35-eb1b-4171-8a54-b610a02b9c5c/tiles/{z}/{x}/{y}?time=%5B%222025-05-12%22%2C%222025-05-13%22%5D"}}]' center=[12.3,45.45] zoom=11.5 animationOptions="{duration:1000}" }-->

#### The Venice Lagoon Ecosystem

Welcome to the Venice Lagoon – the largest lagoon in the Mediterranean Sea, covering approximately 550 square kilometers. This remarkable ecosystem serves as a transition zone between terrestrial and marine environments, creating conditions that support exceptional biodiversity while remaining highly sensitive to environmental changes.

The lagoon's shallow waters (average depth just 1 meter) and restricted exchange with the Adriatic Sea make it particularly vulnerable to eutrophication – the excessive growth of algae due to nutrient enrichment from human activities.

<small>Image: Copernicus [Sentinel-2 L2A 12 May 2025](https://api.explorer.eopf.copernicus.eu/browser/external/api.explorer.eopf.copernicus.eu/stac/collections/sentinel-2-l2a/items/S2C_MSIL2A_20250512T100611_N0511_R022_T32TQR_20250512T173114?.language=en)<br/>Natural color composite (Bands red, green, blue)</small>

### <!--{ layers='[{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/openeo/services/xyz/25107b35-eb1b-4171-8a54-b610a02b9c5c/tiles/{z}/{x}/{y}?time=%5B%222025-05-12%22%2C%222025-05-13%22%5D&color_formula=gamma+rgb+1.45%2C+sigmoidal+rgb+6+0.15%2C+saturation+1.4"}}]' center=[12.4,45.49] zoom=12.3 animationOptions="{duration:1000}" }-->

#### The Visible Problem

Look closely at the water surface – those green to dark patches aren't just shadows or sediment. They're floating mats of cyanobacteria and other algae, visible even from 800 kilometers above Earth.

These surface blooms represent one of the lagoon's most pressing environmental challenges. When conditions are right – warm temperatures, abundant nutrients, and calm waters – cyanobacteria can multiply exponentially, forming dense surface scums that block sunlight and deplete oxygen in the water below.

<small>Image: Copernicus [Sentinel-2 L2A 12 May 2025](https://api.explorer.eopf.copernicus.eu/browser/external/api.explorer.eopf.copernicus.eu/stac/collections/sentinel-2-l2a/items/S2C_MSIL2A_20250512T100611_N0511_R022_T32TQR_20250512T173114?.language=en)<br/>Colored using gamma correction, sigmoidal contrast enhancement, and increased saturation to highlight surface features</small>

### <!--{ layers='[{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/openeo/services/xyz/453c1856-968a-4862-94cc-fe03da7d427a/tiles/{z}/{x}/{y}?time=%5B%222025-05-12%22%2C%222025-05-13%22%5D"}}]' center=[12.4,45.49] zoom=12.3 animationOptions="{duration:1000}" }-->

#### A Closer Look at Algae Accumulation

Let's switch to a different visualization that highlights floating aquatic plants and algae more clearly. This image uses a specialized algorithm designed to detect surface vegetation based on its unique spectral characteristics.

Algae don't distribute evenly across the lagoon. Wind patterns, tidal currents, and the lagoon's complex bathymetry create areas where floating algae concentrate, forming the distinctive patterns visible in satellite imagery.

These accumulations can have serious consequences: they block sunlight needed by underwater vegetation, create anoxic conditions that kill fish and other marine life, and impact the lagoon's aesthetic and economic value for tourism and fishing industries.

<small>Image: Copernicus [Sentinel-2 L2A 12 May 2025](https://api.explorer.eopf.copernicus.eu/browser/external/api.explorer.eopf.copernicus.eu/stac/collections/sentinel-2-l2a/items/S2C_MSIL2A_20250512T100611_N0511_R022_T32TQR_20250512T173114)<br/>Aquatic Plants and Algae Detector (APA Script)</small>

### <!--{ center=[12.3,45.45] zoom=11.5 animationOptions="{duration:1000}" }-->

#### Beyond What the Eye Can See

But what you see on the surface is just part of the story. Chlorophyll-a – the green pigment that enables photosynthesis in cyanobacteria and other algae – exists throughout the water column, not just in visible surface blooms.

Traditional visual observation, whether from boats, aircraft, or even satellites, can only detect the most severe surface accumulations. To truly understand and monitor the extent of algal activity in the lagoon, we need to look beyond the visible spectrum. This is where satellite technology and spectral analysis come into play.

<small>Image: Copernicus [Sentinel-2 L2A 12 May 2025](https://api.explorer.eopf.copernicus.eu/browser/external/api.explorer.eopf.copernicus.eu/stac/collections/sentinel-2-l2a/items/S2C_MSIL2A_20250512T100611_N0511_R022_T32TQR_20250512T173114)<br/>Aquatic Plants and Algae Detector (APA Script)</small>

## Revealing the invisible with satellite spectroscopy <!-- { style="margin-top: 7rem" } -->

### Cyanobacteria Chlorophyll-a NDCI

In order to produce a fast and robust chl-a estimate from S2, the normalized difference chlorophyll index (NDCI) was used to establish an empirically derived chl-a model (Mishra and Mishra, 2012). The NDCI model utilizes the reflectance (Rrs) measured in MSI spectral bands located at 665 nm and 705 nm, which are maximally sensitive to chl-a absorption, and backscattering induced reflectance, respectively. NDCI is calculated by taking the spectral difference of these two bands, and normalizing by their sums, as follows:

```
NDCI = [Rrs(705) – Rrs(665)] / [Rrs(705) + Rrs(665)]        (1)
```

The index was trained on synthetic data with the following restrictions to limit uncertainty due to extreme cases:

1. Concentration of non-algal particles (Cnap) < 10 ug/L
2. Absorption due to coloured dissolved organic matter (CDOM) < 3 m-1
3. Chl-a concentrations less than 500 ug/L
4. Only cyanobacteria M. aeruginosa used in training.

This resulting in 9836 samples, which were separated into a training dataset of 7868 samples (80%) and a dataset to test the predictive capability of the model of 1968 samples (20%). An exponential model resulted in the best fit on the training data (eq. 2) based on Pearson correlation coefficient (R2=0.52), with predictive statistics shown in the figure below.

```
Chl-a = 17.441e(4.7038*NDCI)        (2)
```

![Calibration](https://github.com/EOPF-Explorer/narratives/blob/ndci/chl-ndci/calibration.png?raw=true)

## Applying NDCI to Venice Lagoon <!--{ as="eox-map" class="overlay-br" mode="tour" }-->

<div style="height: 22rem; font-size: 0.9rem; margin-top: 1rem; margin-bottom: 1rem; border-radius: 2px;">
<strong>Chlorophyll-a Concentration Levels:</strong>

<table style="margin: 0; border-collapse: collapse;">
  <thead>
    <tr style="border-bottom: 1px solid #ddd;">
      <th style="padding: 2px 6px; text-align: left; font-weight: 600; font-size: 0.75rem;">Color</th>
      <th style="padding: 2px 6px; text-align: left; font-weight: 600; font-size: 0.75rem;">Chl-a (μg/L)</th>
      <th style="padding: 2px 6px; text-align: left; font-weight: 600; font-size: 0.75rem;">Quality</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="padding: 2px 6px; color: #000080; font-weight: 500; font-size: 0.75rem;">Deep Blue</td>
      <td style="padding: 2px 6px; font-size: 0.75rem;">< 0.5</td>
      <td style="padding: 2px 6px; font-size: 0.75rem;">Ultra-oligotrophic (very clear)</td>
    </tr>
    <tr>
      <td style="padding: 2px 6px; color: #0066FF; font-weight: 500; font-size: 0.75rem;">Blue</td>
      <td style="padding: 2px 6px; font-size: 0.75rem;">0.5 - 2.5</td>
      <td style="padding: 2px 6px; font-size: 0.75rem;">Oligotrophic (clear)</td>
    </tr>
    <tr>
      <td style="padding: 2px 6px; color: #00BFFF; font-weight: 500; font-size: 0.75rem;">Blue-Cyan</td>
      <td style="padding: 2px 6px; font-size: 0.75rem;">2.5 - 8</td>
      <td style="padding: 2px 6px; font-size: 0.75rem;">Mesotrophic (moderate)</td>
    </tr>
    <tr>
      <td style="padding: 2px 6px; color: #228B22; font-weight: 500; font-size: 0.75rem;">Green</td>
      <td style="padding: 2px 6px; font-size: 0.75rem;">8 - 24</td>
      <td style="padding: 2px 6px; font-size: 0.75rem;">Eutrophic (nutrient-rich)</td>
    </tr>
    <tr>
      <td style="padding: 2px 6px; color: #FFD700; font-weight: 500; font-size: 0.75rem;">Yellow</td>
      <td style="padding: 2px 6px; font-size: 0.75rem;">24 - 75</td>
      <td style="padding: 2px 6px; font-size: 0.75rem;">Highly eutrophic</td>
    </tr>
    <tr>
      <td style="padding: 2px 6px; color: #FF8C00; font-weight: 500; font-size: 0.75rem;">Orange</td>
      <td style="padding: 2px 6px; font-size: 0.75rem;">75 - 150</td>
      <td style="padding: 2px 6px; font-size: 0.75rem;">Hypereutrophic</td>
    </tr>
    <tr>
      <td style="padding: 2px 6px; color: #DC143C; font-weight: 500; font-size: 0.75rem;">Red</td>
      <td style="padding: 2px 6px; font-size: 0.75rem;">> 150 or FAI > 0.08</td>
      <td style="padding: 2px 6px; font-size: 0.75rem;">Severe bloom / Floating algae</td>
    </tr>
  </tbody>
</table>
</div>
<!--{ style="opacity: 0.75; font-size: 1rem;" }-->

### <!--{ layers='[{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/openeo/services/xyz/9551a434-c1a9-4600-bddb-d289f55c670e/tiles/{z}/{x}/{y}?time=%5B%222025-05-12%22%2C%222025-05-13%22%5D"}}]' center=[12.3,45.45] zoom=11.5 animationOptions="{duration:1000}" }-->

#### Exploring chlorophyll patterns across the lagoon

Now let's see the same area through a different lens. This visualization shows the Normalised Difference Chlorophyll Index (NDCI)

Using Sentinel-2 satellite bands, the formula described in the previous section becomes:

```
(B05 - B04) / (B05 + B04)
```

The "red edge" band (B05 at 705nm) is particularly sensitive to chlorophyll-a because it sits at the boundary where vegetation and algae transition from absorbing to reflecting light. By comparing this to the standard red band (B04 at 665nm), NDCI can detect chlorophyll-a even when it's not visible to the human eye.

Notice how this spectral view reveals extensive chlorophyll-a distribution throughout the lagoon – far more than what was visible in the natural color imagery above.

### <!--{ center=[12.34,45.51] zoom=13.8 animationOptions="{duration:1000}" }-->

#### Northern Lagoon: Industrial Influence Zone

The northern section of the lagoon, near the Marghera industrial complex, shows distinctive chlorophyll-a patterns influenced by nutrient loading from industrial and urban sources. The higher concentrations (shown in yellow-green) often correlate with areas receiving freshwater inflow carrying nitrogen and phosphorus from mainland sources.

### <!--{ center=[12.35,45.44] zoom="13.8" animationOptions="{duration:800}" }-->

#### Central Lagoon: Venice Historic Center

Around Venice's historic islands, chlorophyll-a distribution reflects the complex interplay between urban runoff, boat traffic, and tidal mixing. The intricate channel system creates varying conditions – some areas show elevated chlorophyll levels while others remain relatively clear due to better water exchange with the Adriatic Sea.

### <!--{ center=[12.26,45.25] zoom="13.2" animationOptions="{duration:800}" }-->

#### Southern Lagoon: Chioggia and Natural Areas

The southern lagoon presents a mix of natural and anthropogenic influences. Areas near Chioggia show impacts from fishing activities and aquaculture, while more isolated regions display chlorophyll patterns driven primarily by natural seasonal cycles and nutrient availability.

### <!--{ layers='[{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/openeo/services/xyz/9551a434-c1a9-4600-bddb-d289f55c670e/tiles/{z}/{x}/{y}?time=%5B%222025-05-12%22%2C%222025-05-13%22%5D"}}]' center=[12.3,45.45] zoom=11.5 animationOptions="{duration:1000}" }-->

#### Spring 2025: The Awakening

As water temperatures rise and daylight hours increase, cyanobacteria begin their annual cycle of growth. Spring conditions in the Venice Lagoon typically show moderate chlorophyll-a levels, with activity concentrated in nutrient-rich areas near freshwater inputs.

### <!--{ layers='[{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/openeo/services/xyz/9551a434-c1a9-4600-bddb-d289f55c670e/tiles/{z}/{x}/{y}?time=%5B%222025-07-03%22%2C%222025-07-04%22%5D"}}]' center=[12.3,45.45] zoom=11.5 animationOptions="{duration:300}" }-->

#### Summer 2025: Peak Activity

Summer brings optimal conditions for cyanobacteria growth: warm water temperatures, intense sunlight, and calm weather. The NDCI visualization reveals extensive chlorophyll-a distribution across much of the lagoon, with particularly high concentrations in shallow, protected areas with limited water exchange.

### <!--{ layers='[{"type":"Tile","properties":{"id":"background"},"source":{"type":"WMTSCapabilities","url":"https://tiles.maps.eox.at/wmts/1.0.0/WMTSCapabilities.xml","layer":"s2cloudless-2022_3857"}},{"type":"Tile","properties":{"id":"s-2-l2a"},"source":{"type":"XYZ","url": "https://api.explorer.eopf.copernicus.eu/openeo/services/xyz/9551a434-c1a9-4600-bddb-d289f55c670e/tiles/{z}/{x}/{y}?time=%5B%222025-10-24%22%2C%222025-10-25%22%5D"}}]' center=[12.3,45.45] zoom=11.5 animationOptions="{duration:300}" }-->

#### Autumn 2025: Natural Decline

As temperatures drop and storm activity increases, chlorophyll-a concentrations naturally decline across most of the lagoon. The spectral signature reveals this seasonal transition, with only the most nutrient-rich areas maintaining elevated chlorophyll levels.

This temporal sequence demonstrates how satellite monitoring provides continuous, objective assessment of water quality changes that would be impossible to track through visual observation alone.

## Here's how we built this <!-- { style="margin-top: 7rem" } -->

Want to build your own cyanobacteria monitoring system? The visualization you've just experienced is powered by cutting-edge cloud-native geospatial technologies that make satellite-based water quality monitoring accessible to researchers, environmental managers, and concerned citizens worldwide.

### 🔧 Core Processing Engine : [openEO by TiTiler](https://github.com/sentinel-hub/titiler-openeo)

This monitoring system is powered a custom version of openEO dedicated for reading and processing EOPF Zarr Sentinels, combining the power of openEO graphs with the cloud-based on-the-fly visualization capabilities of TiTTiler. The live API serving this demo is available at:

**`https://api.explorer.eopf.copernicus.eu/openeo/`**

You can reproduce, experiment and deploy you own openEO defined processes using a set of tools at you disposal on the EOPF Explorer platform:

1. The **[NDCI Cyanobacteria Jupyter Notebook](https://github.com/EOPF-Explorer/narratives/blob/main/chl-ndci/openeo_ndci_cyanobacteria.ipynb)** available in the narratives repository of the project.
2. **[openEO Studio](https://explorer.eopf.copernicus.eu/openeo-studio/)** - a visual interface to get started with openEO python API without caring about deploying any coding environment.
3. **[openEO Web Editor](https://editor.openeo.org/?server=https%3A%2F%2Fapi.explorer.eopf.copernicus.eu%2Fopeneo%2F)** - a web-based graphical editor to create and test openEO process graphs directly in your browser as well as deploy them as web services or user-defined processes.

### 📊 Data Source and Catalog

All satellite imagery comes from the Copernicus Sentinel-2 mission, accessed through our comprehensive data catalog:

**`https://api.explorer.eopf.copernicus.eu/browser/`**

### 🚀 Dynamic NDCI Processing

What you're seeing above is **dynamically computed NDCI** – no preprocessing required! The system calculates the Normalised Difference Chlorophyll Index on-the-fly using openEO graph deployed as a tiling web service.

The NDCI calculation `(B05-B04)/(B05+B04)` is processed in real-time for any date and location in our archive. This approach enables responsive environmental monitoring applications without the need for complex data preprocessing pipelines – just point to the data you need and let the API handle the rest!

<div style="height: 7rem"></div>

## Credits <!-- { style="margin-top: 7rem" } -->

This demonstration was developed by [Development Seed](https://developmentseed.org/) as part of the [EOPF Explorer project](https://explorer.eopf.copernicus.eu/), funded by the [European Union's Copernicus Programme](https://www.copernicus.eu/en) under grant agreement No 101100712.

The underlying APA and cyanobacteria chlorophyll-a processes are largely inspired by the Sentinel Hub custom scripts:

- [Aquatic Plants and Algae Detector (APA)](https://custom-scripts.sentinel-hub.com/custom-scripts/sentinel-2/aquatic-plants-and-algae-detector-apa/)
- [Cyanobacteria Chlorophyll-a Visualization](https://custom-scripts.sentinel-hub.com/custom-scripts/sentinel-2/cyanobacteria-chlorophyll-a-visualization/)
