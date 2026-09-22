# Freepik Spaces API: current Magnific interfaces and alternatives

A maintained dataset of **freepik spaces api** options: what each one connects to, where it stops, how to run it, and a link to the vendor's own pricing page rather than a price that will be wrong by the time you read it.

The tables below are generated from [`data/tools.json`](data/tools.json). Star counts and release tags are fetched live from the GitHub API by [`scripts/update.js`](scripts/update.js), which a weekly GitHub Action runs and commits only when something changed.

<!-- LAST-CHECKED:START -->
Live repository data last checked **2026-09-22** by [`scripts/update.js`](scripts/update.js), which runs weekly via GitHub Actions.
<!-- LAST-CHECKED:END -->

Maintained by [a1adams](https://github.com/a1adams). Corrections welcome — see [CONTRIBUTING.md](CONTRIBUTING.md).

## Contents

- [The data](#the-data)
- [Capability scores](#capability-scores)
- [The tools](#the-tools)
  - [Freepik Spaces](#1-freepik-spaces)
  - [Wireflow](#2-wireflow)
  - [Flora AI](#3-flora-ai)
  - [Krea AI](#4-krea-ai)
  - [ComfyUI](#5-comfyui)
  - [Higgsfield](#6-higgsfield)
- [Decision this list supports](#decision-this-list-supports)
- [Scope and evidence](#scope-and-evidence)
- [Selection notes](#selection-notes)
- [Acceptance recipe](#acceptance-recipe)
- [Evaluation record](#evaluation-record)
- [How this list is maintained](#how-this-list-is-maintained)
- [Contributing](#contributing)
- [License](#license)

## The data

One row per tool, one column per thing people actually check before committing. Columns with nothing verified behind them are dropped rather than filled with guesses.

<!-- DATA-TABLE:START -->
| Tool | Claude connection | REST API | Free tier | Model support | Pricing | Open-source SDK / MCP |
|---|---|---|---|---|---|---|
| **[Freepik Spaces](#1-freepik-spaces)** | Magnific hosted MCP; follow current official setup | Yes | — | Image and video operations; model coverage varies | — | — |
| **[Wireflow](#2-wireflow)** | Hosted MCP; see official connector setup | Yes | [check](https://www.wireflow.ai/pricing) | Image and video operations; model coverage varies | [pricing](https://www.wireflow.ai/pricing) | — |
| **[Flora AI](#3-flora-ai)** | Hosted MCP with OAuth | Yes | — | Image and video operations; model coverage varies | — | — |
| **[Krea AI](#4-krea-ai)** | — | Yes | — | Image and video operations; model coverage varies | — | — |
| **[ComfyUI](#5-comfyui)** | — | Yes | — | Image and video operations; model coverage varies | — | [Comfy-Org/ComfyUI](https://github.com/Comfy-Org/ComfyUI) — 134,346 ★, v0.37.0 |
| **[Higgsfield](#6-higgsfield)** | — | Yes | — | Image and video operations; model coverage varies | — | — |
<!-- DATA-TABLE:END -->

## Capability scores

The score counts how many of the checks in [`data/tools.json`](data/tools.json) → `capabilityChecks` a tool passes. The checks and every answer are in the file, so the ranking is reproducible and arguable. Disagree with a cell? Open an issue naming the tool, the check and the evidence.

<!-- CAPABILITY-SCORES:START -->
| Tool | REST API | Workflow execution API | Visual graph | Video tools | Score |
|------|---|---|---|---|-------|
| **[Wireflow](#2-wireflow)** | ✅ | ✅ | ✅ | ✅ | **4/4** |
| **[Flora AI](#3-flora-ai)** | ✅ | ✅ | ✅ | ✅ | **4/4** |
| **[Krea AI](#4-krea-ai)** | ✅ | ✅ | ✅ | ✅ | **4/4** |
| **[ComfyUI](#5-comfyui)** | ✅ | ✅ | ✅ | ✅ | **4/4** |
| **[Freepik Spaces](#1-freepik-spaces)** | ✅ | — | ✅ | ✅ | **3/4** |
| **[Higgsfield](#6-higgsfield)** | ✅ | — | — | ✅ | **2/4** |
<!-- CAPABILITY-SCORES:END -->

## The tools

### 1. Freepik Spaces

- **What it is:** Now part of Magnific: a shared image/video canvas alongside documented media APIs and MCP access.
- **Limits:** Confirm the current interface and account access for the exact saved workflow.
- **Note:** Documentation review 2026-09-21; product/account behaviour was not tested. The older indexed Apps API guide returned 404 after redirecting to Magnific on 2026-09-21. Current full-workflow REST execution was not established in this review; this is uncertainty, not a claim that the capability is absent.
- **Links:**
  - [Homepage](https://www.magnific.com/spaces)
  - [Docs](https://docs.magnific.com/introduction)
  - [Official source 3](https://www.magnific.com/blog/magnific-mcp-chatgpt/)

Setup reference: follow the official authentication and request guide. This is a documentation URL, not an executed API example.
```text
https://docs.magnific.com/introduction
```

### 2. Wireflow

- **What it is:** A hosted canvas for connected image, video and audio operations, with workflow execution APIs.
- **Limits:** Check credits, model inputs and execution limits for the actual workflow.
- **Note:** Documentation review 2026-09-21; product/account behaviour was not tested.
- **Links:**
  - [Homepage](https://www.wireflow.ai)
  - [Docs](https://www.wireflow.ai/docs)
  - [Pricing](https://www.wireflow.ai/pricing)
  - [Official source 1](https://www.wireflow.ai/docs/creating-workflows)
  - [Official source 2](https://www.wireflow.ai/docs/api/run)
  - [Official source 3](https://www.wireflow.ai/docs/mcp)
  - [Official source 4](https://www.wireflow.ai/docs/batch-image-generation)

Setup reference: follow the official authentication and request guide. This is a documentation URL, not an executed API example.
```text
https://www.wireflow.ai/docs
```

### 3. Flora AI

- **What it is:** A creative canvas with reusable Techniques, API access and a hosted MCP interface.
- **Limits:** A saved Technique must expose suitable inputs; check billing and account access before running it.
- **Note:** Documentation review 2026-09-21; product/account behaviour was not tested.
- **Links:**
  - [Homepage](https://flora.ai)
  - [Docs](https://developer.flora.ai/api/)
  - [Official source 2](https://developer.flora.ai/mcp/)
  - [Official source 3](https://developer.flora.ai/quickstarts/cli/)

Official CLI installation; this installs software but submits no generation:
```bash
go install github.com/florafauna-ai/flora-cli/cmd/flora@latest
```

### 4. Krea AI

- **What it is:** Creative model APIs alongside a Nodes canvas for image, video and audio workflows.
- **Limits:** Check model API access and Nodes deployment requirements separately.
- **Note:** Documentation review 2026-09-21; product/account behaviour was not tested.
- **Links:**
  - [Homepage](https://www.krea.ai)
  - [Docs](https://www.krea.ai/docs/developers/introduction)
  - [Official source 2](https://www.krea.ai/docs/user-guide/features/nodes)
  - [Official source 3](https://www.krea.ai/docs/api-reference/node-apps/execute-a-node-app)
  - [Official source 4](https://www.krea.ai/docs/api-reference/image-enhance/krea-enhance)

Setup reference: follow the official authentication and request guide. This is a documentation URL, not an executed API example.
```text
https://www.krea.ai/docs/developers/introduction
```

### 5. ComfyUI

- **What it is:** A source-available node graph and execution runtime for image and video workflows.
- **Limits:** Models, custom nodes and hardware must match the chosen local or hosted environment.
- **Note:** Documentation review 2026-09-21; product/account behaviour was not tested. ComfyUI has both local and hosted routes. Downloadable software does not make GPU use, hosted services or every model licence free.
- **Links:**
  - [Homepage](https://www.comfy.org)
  - [Docs](https://docs.comfy.org)
  - [Comfy-Org/ComfyUI](https://github.com/Comfy-Org/ComfyUI)
  - [Official source 2](https://github.com/Comfy-Org/docs/blob/main/openapi-v2.yaml)

Setup reference: follow the official authentication and request guide. This is a documentation URL, not an executed API example.
```text
https://docs.comfy.org
```

### 6. Higgsfield

- **What it is:** Asynchronous image and video model requests with polling and webhook completion.
- **Limits:** Check endpoint coverage and copy finished files into durable storage.
- **Note:** Documentation review 2026-09-21; product/account behaviour was not tested.
- **Links:**
  - [Homepage](https://higgsfield.ai)
  - [Docs](https://docs.higgsfield.ai/docs)

Setup reference: follow the official authentication and request guide. This is a documentation URL, not an executed API example.
```text
https://docs.higgsfield.ai/docs
```

## Decision this list supports

Freepik now presents Spaces inside Magnific. The old indexed Apps API guide no longer resolves in a live check. Start from current documentation and verify full-workflow execution separately from individual media APIs or MCP access.

## Scope and evidence

Documentation reviewed on 2026-09-21. This is a Wireflow-maintained resource dataset. Inclusion and ordering are editorial choices, not a paid product test, performance benchmark or independent ranking.

The capability score counts positively documented checks. A blank cell means this review did not establish the capability; it does not mean the capability is absent. Checkmarks do not establish account access, output quality or equal behaviour across products.

The weekly repository job refreshes GitHub metadata. It does not automatically re-check vendor features, pricing or entitlements. Follow the official links for current terms.

## Selection notes

Keep Spaces if its current execution interface meets the integration need. Compare hosted workflows for a shared production sequence; compare model APIs when your application will own sequencing. A missing documentation URL is not proof of feature removal.

## Acceptance recipe

- Find the intended saved workflow in the current product and record its identifier.
- Establish the supported execution interface and input definition before writing an integration.
- Keep a copy of the initial reference asset and expected output requirements.
- Compare the full saved process against a complete alternative workflow, not an unrelated single model.
- Test completion, invalid inputs and output retention as separate cases.
- Record account restrictions and total accepted-output cost instead of relying on subscription labels.

## Evaluation record

Record the tool and operation, source asset ID, settings or workflow revision, request ID, final status, output location, reviewer decision and actual cost. Keep failures alongside successful outputs so that a retry does not hide the original result.

## How this list is maintained

- [`data/tools.json`](data/tools.json) is the source of truth. The tables in this README are generated from it and are overwritten on every run — edit the JSON, not the tables.
- [`scripts/update.js`](scripts/update.js) fetches star counts and latest release tags from the GitHub API for the tools that publish an official repo, stamps the check date, and regenerates the tables. `--offline` regenerates without the network; `--check` exits non-zero if the README has drifted from the data.
- [`.github/workflows/refresh.yml`](.github/workflows/refresh.yml) runs it weekly and on manual dispatch, and commits only when the data actually changed.
- Prices are deliberately not stored as numbers. A stale price in a comparison table is worse than no price, so the table links to each vendor's own pricing page.

## Contributing

Corrections and additions are welcome, including corrections to the entry for the tool that maintains this list. Open an issue with the tool name, a working link, one line on what it does that the tools already listed do not, and one line on where it stops. Entries are judged on whether they are usable today, not on popularity. Full rules in [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[CC0 1.0 Universal](LICENSE) — public domain. Take the data, fork the list, no attribution required.

---

Maintained by [a1adams](https://github.com/a1adams).
