# EOPF-Explorer Narratives

This is a collection of stories that showcase the benefits of on-the-fly rendering of Copernicus Sentinel satellite data, powered by ESA's new cloud-native EOPF Sentinel Zarr format, under the [EOPF Sentinel Zarr Explorer](https://explorer.eopf.copernicus.eu/).

The subject of the stories are phenomena of our natural / physical world that can be visualised with satellite imagery.

The technical features they demonstrate are:
* Scrollytelling with an accessible, declarative document format (Markdown), powered by [eodash](https://github.com/eodash/eodash/).
* Embedded maps that dynamically load satellite imagery from [visualisation-optimised EOPF Zarr](https://explorer.eopf.copernicus.eu/software-services/datamodel/)
* Server-side rendering of imagery transformed with band math using [TiTiler-EOPF](https://github.com/EOPF-Explorer/titiler-eopf) and advanced algorithms using [TiTiler-openEO](https://github.com/sentinel-hub/titiler-openeo)
* Client-side rendering with [OpenLayers](https://explorer.eopf.copernicus.eu/software-services/ol/) reading EOPF Zarr directly from cloud storage

All stories also include a section about the services and software features they rely on. Thanks to these features, the authoring of the stories requires no data pre-processing – you can start writing right away. 

## Coding agents

There is an MCP (Model Context Protocol) service available that enables coding agents (Copilot, Claude Code, et al.) to compose the eodash storytelling elements reliably. Details will follow shortly.


## Catalogue persistence

The [EOPF Explorer STAC catalogue](https://api.explorer.eopf.copernicus.eu/browser/) currently features a rolling archive of Sentinel-2 L2A data in visualisation-optimised GeoZarr, soon to be expanded with Sentinel-1 data. 

Data that is featured in stories will remain published throughout the duration of the project.


## License

All content is published under CC0 (Public Domain). See LICENSE.


## Questions and support

Please reach out on the [EOPF Discourse forum](https://discourse.eopf.copernicus.eu/c/eopf-explorer/).
