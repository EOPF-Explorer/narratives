# EOPF-Explorer Narratives

This is a collection of stories that showcase the benefits of on-the-fly rendering of Copernicus Sentinel satellite data, powered by ESA's new cloud-native EOPF Sentinel Zarr format, under the [EOPF Sentinel Zarr Explorer](https://explorer.eopf.copernicus.eu/).

The subject of the stories are phenomena of our natural / physical world that can be visualised with satellite imagery.

The technical features they demonstrate are:
* Scrollytelling with an accessible, declarative document format (Markdown), powered by [eodash](https://github.com/eodash/eodash/).
* Embedded maps that dynamically load satellite imagery from [visualisation-optimised EOPF Zarr](https://explorer.eopf.copernicus.eu/software-services/datamodel/)
* Server-side rendering of imagery transformed with band math using [TiTiler-EOPF](https://github.com/EOPF-Explorer/titiler-eopf) and advanced algorithms using [TiTiler-openEO](https://github.com/sentinel-hub/titiler-openeo)
* Client-side rendering with [OpenLayers](https://explorer.eopf.copernicus.eu/software-services/ol/) reading EOPF Zarr directly from cloud storage

All stories also include a section about the services and software features they rely on. Thanks to these features, the authoring of the stories requires no data pre-processing – you can start writing right away. 

## Contributions welcome

We welcome contributions. Please note our license and the following instructions:

### Structure

- Markdown story files must be placed in the **root of the repository** to be picked up by the storytelling engine.
- Do **not** store assets (images, videos, data files) in this repo.

### Assets

Upload assets to [EOPF-Explorer/eodash-assets](https://github.com/EOPF-Explorer/eodash-assets) and reference them via:

- GitHub raw URL: `https://raw.githubusercontent.com/EOPF-Explorer/eodash-assets/main/<path>`
- rawgit CDN (cache-friendly): `https://raw.githack.com/EOPF-Explorer/eodash-assets/main/<path>`

### Preview

When a pull request is opened, a bot will post a comment with a link to the live preview of the story. No manual steps required.

## Coding agents

The [EOxElements MCP](https://eox-a.github.io/EOxElements/?path=/docs/coding-agents--docs) (Model Context Protocol) service is available to enable coding agents (Copilot, Claude Code, et al.) to compose the eodash storytelling special markdown syntax reliably.

### Installation

**Option 1 -- hosted server (no install required):**

Add `https://elements.mcp.eox.at` as an MCP server in your coding agent settings.

**Option 2 -- local install:**

```bash
npm install -g @eox/elements-mcp-server
elements-mcp-server
```
The server will be available at `http://localhost:3000/mcp`. Add that URL as an MCP server in your coding agent settings.

### Starter prompt

Use the following prompt to get started:

```prompt
Use the EOxElements MCP to fetch the `eox-storytelling` element stories and documentation.
Read through the fetched stories to understand the special markdown syntax -- the available
section types, map blocks, chart blocks, metadata properties, and any other supported elements.

Once you have a clear picture of the syntax, ask me what narrative I want to write. I will
describe the topic, the data sources, and the message I want to convey. You will then draft
a `.md` story file in the root of this repository following the eox-storytelling markdown
conventions you learned.

If a block type or property is unclear, re-fetch the relevant story
example from the MCP before writing.
```



## Catalogue persistence

The [EOPF Explorer STAC catalogue](https://api.explorer.eopf.copernicus.eu/browser/) currently features a rolling archive of Sentinel-2 L2A data in visualisation-optimised GeoZarr, soon to be expanded with Sentinel-1 data. 

Data that is featured in stories will remain published throughout the duration of the project.


## License

All content is published under CC0 (Public Domain). See [LICENSE](./LICENSE).


## Questions and support

Please reach out on the [EOPF Discourse forum](https://discourse.eopf.copernicus.eu/c/eopf-explorer/).
