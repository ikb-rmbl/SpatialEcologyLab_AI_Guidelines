# RMBL Data Hub — tools you can use

The lab maintains a set of tools (the **RMBL Data Hub**, [data.rmbl.org](https://data.rmbl.org)) that take a lot of the friction out of finding data, writing starter code, getting compute, and grounding the AI assistant in real research. **Use them if they fit your project — none of this is mandatory.** Most students will at least use the SDP Browser and the Knowledge Commons; the Compute Hub is there when your data is too big to work with on your laptop.

Everything here is **plumbing** (it removes friction), not **science** (it doesn't do your thinking) — see the note at the end. Two of these tools *generate code for you*, which is great until it becomes copy-paste-without-understanding. The explanation gate still applies: if you keep generated code, you explain it first.

| Tool | URL | Auth | Use it to… |
|------|-----|------|-----------|
| **Knowledge Commons** | [rmblknowledgecommons.org](https://rmblknowledgecommons.org) | None | Find papers, datasets, and prior work; ground the AI in real sources |
| **SDP Browser** | [sdpbrowser.org](https://sdpbrowser.org) | None | Discover, preview, and extract SDP rasters with no code; generate `rSDP`/`pySDP` starter code |
| **Compute Hub** | [rmblcomputehub.org](https://rmblcomputehub.org) | GitHub (allowlist) | Run analyses in the cloud, next to the data, with everything pre-installed |
| **rSDP / pySDP** | [github.com/rmbl-sdp](https://github.com/rmbl-sdp) | None | The R/Python client packages for SDP data — the workhorses |

---

## Knowledge Commons — discovery + grounding the assistant

A searchable, connected index of ~5,000 publications, ~1,400 datasets, plus theses, community docs, and news for the Gunnison Basin — with species, places, protocols, and concepts linked across them.

**For your literature work:**
- **Search** ([/search](https://rmblknowledgecommons.org/search)) combines keyword *and* semantic search, so it surfaces related work even when the terminology differs.
- **Explore / neighborhoods / frontiers** give synthesized higher-level views of research communities and open questions — a fast way to orient in a new subfield.
- **Related works** are computed from semantic similarity, shared entities, co-authorship, and citation networks.
- **Citation export** in RIS and BibTeX (whole result sets at once) → straight into Zotero/EndNote.

**For your AI assistant (the high-leverage part):**
- There's an **MCP server** at `https://rmblknowledgecommons.org/api/mcp`. The Posit Assistant in Positron supports MCP, so you can connect it (steps below) and the assistant will **search the Commons and cite real RMBL sources instead of making things up.** This is the single best way to use AI for literature here — it turns "the AI said so" into "the AI found this paper, which says so," with a link you can check.
- There's also a plain **REST API** at `https://rmblknowledgecommons.org/api/v1` (rate-limited, no key) if you want to query it from code, and a `/llms.txt` discovery file.

> **Why this matters for the way we work:** grounding the assistant in the Commons is the "verify against reality" pattern ([handbook/03](../handbook/03-working-with-the-assistant.md)) built into the tool. It still doesn't read the papers *for* you — you do that — but it stops the assistant from inventing citations, which it will otherwise do confidently.

### Connecting the Commons to Posit Assistant (Positron)

1. Open the Command Palette (`Cmd/Ctrl+Shift+P`) → **Preferences: Open User Settings (JSON)**.
2. Add the `assistant.mcpServers` block below to the top-level object (merge it with whatever's already there — don't create a second `{ }`):

   ```jsonc
   {
     // ...your existing settings...
     "assistant.enabled": true,
     "positron.assistant.enable": true,
     "assistant.mcpServers": {
       "rmbl-knowledge-commons": {
         "url": "https://rmblknowledgecommons.org/api/mcp",
         "type": "remote",
         "transport": "http"
       }
     }
   }
   ```
3. Save, then **reload Positron** (Command Palette → *Developer: Reload Window*, or just restart).
4. **Confirm it worked:** ask the assistant something like *"Search the RMBL Knowledge Commons for papers on snowmelt timing and list three with links."* If it returns real records with URLs, you're connected.

**Project-scoped alternative (handy for shared project repos):** the same `assistant.mcpServers` block can go in a **`.vscode/settings.json`** at your project root instead of (or in addition to) User Settings — so anyone who clones the project gets the Commons wired up. The lab's [project skeleton](../templates/project-skeleton/) ships with exactly this file. *Project-scoped MCP is newer and not fully confirmed across Positron versions — if the assistant doesn't pick it up, fall back to User Settings, which always works.*

> **Privacy note:** with this enabled, the queries the assistant runs against the Commons leave your machine and hit RMBL's server. That's RMBL's own public research corpus, so it's fine for research use — just know it's a network call, like any web search.

If you spot a wrong attribution or duplicate, you can flag it on the site; a curator fixes it.

---

## SDP Browser — find data and get starter code without writing any

A no-code, point-and-click window into the Spatial Data Platform catalog (~160 collections: snow, climate, land cover, terrain, imagery). The data underneath is the **same** openly-readable COGs on `s3://rmbl-sdp/` (us-east-2) that the packages read — so what you preview is exactly what you'll analyze.

**What you can do:**
- **Discover** with faceted search (domain, release, product type, resolution, bands). Deprecated products are flagged — don't use those.
- **Preview** COGs on an interactive map with sensible contrast, unit-aware scaling, scientific colormaps, multi-band composites, and time-series animation.
- **Extract** by drawing an area of interest: zonal stats (min/mean/median/max/sd/histograms), clipped GeoTIFFs, or PNGs.
- **Generate code** — the **recipe generator** produces ready-to-run `rSDP` (`sdp_get_raster()` + clip) or `pySDP` (`open_raster()` + `rio.clip_box()`) snippets, and can export whole notebooks / R Markdown docs.
- **Share** — the full app state (layers, styling, date, view, filters) is encoded in the URL, so a link is a reproducible snapshot.

**Catalog IDs are the lingua franca.** Products have six-character codes (e.g., `R3D009`, `R4D004`). The ID you click in the Browser is the same one you pass to `sdp_get_raster()` (R) or `open_raster()` (Python). The shared STAC catalog lives at `s3://rmbl-sdp/stac/v1/catalog.json`.

> **The catch:** the recipe generator hands you working code. That's a head start, not a finished result. Read it, run it, and **explain it before you keep it** — the recipe is a great thing to ask the assistant to walk you through line by line.

**Typical flow:** explore and validate visually in the Browser → grab the catalog ID and recipe → continue in `rSDP`/`pySDP` locally (Positron) or on the Compute Hub for the real analysis.

---

## Compute Hub — cloud analysis next to the data

A browser-based analysis environment (JupyterHub on AWS, in the same region as the data) with everything pre-installed. Reach for it when your data is **too big to pull onto your laptop**, when you need the shared environment, or when local setup is fighting you. For everyday work we still use **Positron locally**; the Compute Hub is the heavy-lifting option, not a replacement.

**Access:** Sign in at [rmblcomputehub.org](https://rmblcomputehub.org) with **GitHub OAuth** — your GitHub account from [the Git onboarding](../handbook/01-git-and-github.md) is your login. It's restricted to an allowlist of RMBL collaborators; ask your supervisor (or ikb@rmbl.org) to be added.

**What you get:**
- **JupyterLab**, **RStudio Server**, and a **terminal** — pick your interface. (Note: it's RStudio in the cloud, not Positron.)
- **Resource profiles** chosen at login: Small (2 CPU/8 GB) for coding up to Large (8 CPU/32 GB), plus a GPU option. The cluster scales to zero when idle.
- **Pre-installed stack:** Python (`xarray`, `dask`, `rioxarray`, `geopandas`, `zarr`, `netCDF4`, `s3fs`) and R (`terra`, `sf`, `stars`, `tidyverse`), with `pysdp`/`rSDP` ready to import and consistent GDAL/PROJ/GEOS.
- **Data access:** SDP via `sdp_get_catalog()`/`sdp_get_raster()` (R) or `get_catalog()`/`open_raster()` (Python), loaded lazily. CHESS hyperspectral (NEON AOP, 426-band) lives in the `rmbl-chess-data` bucket, reachable via virtual Zarr stores or a FUSE mount at `/data/shared/`.
- **Tutorials:** a `Welcome.ipynb` and `tutorials/` folder (`01_sdp_catalog_basics`, `02_sdp_with_dask`, … `05_sdp_basics_R`) — a good first afternoon.

**Things that will bite you if you don't know them:**
- **Sessions get idle-culled** after ~30–60 min and have a hard cap (~4–8 h). Files on your **50 GB home directory persist**; anything only in kernel memory does **not** — re-running from saved code is the safe habit (and good reproducibility).
- **Installing extra packages:** in Python use `pip install --user ...` (plain `pip install` is wiped on restart); in R `install.packages(...)` persists to your home library.
- Home directories are private to you.

---

## Choosing among them (rough guide)

- *"Has someone studied this? What data exists?"* → **Knowledge Commons** (and connect it to your assistant).
- *"What SDP layer do I want, and what does it look like?"* → **SDP Browser**.
- *"Write and run the actual analysis."* → **Positron locally** with `rSDP`/`pySDP`, or the **Compute Hub** if the data is big or you need the shared environment.

---

## The friction-vs-thinking line (still holds)

Every tool here removes *friction*: it finds data, previews it, generates boilerplate, provides compute, or grounds the assistant in real sources. **None of it removes the *thinking*** — choosing the right data, deciding the method, interpreting the result, and judging whether an answer is believable are still yours. Two specific reminders:

- Code from the **SDP Browser recipe generator** or a Compute Hub tutorial is a starting point you must understand before you keep it (explanation gate).
- The **Knowledge Commons** makes the assistant cite real papers — but *you* still read them and decide what they mean.

When you put any of this into a project `AGENTS.md`, copy the **plumbing** (which tool, which catalog IDs, which packages, the MCP URL) — not conclusions about your data.
