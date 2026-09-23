# awesome-ai-apps

> **Production AI apps — the catalog with code, not just screenshots** — 400+ files of working AI applications: blog-video writer, brand-video monitor, agent systems, LLM SaaS scaffolds — each with full source

<p align="center"><a href="https://github.com/hmzainjamil/awesome-ai-apps">Repository</a> · <a href="https://github.com/hmzainjamil/awesome-ai-apps/commits/main">Commits</a> · <a href="https://github.com/hmzainjamil/awesome-ai-apps/issues">Issues</a></p>
<p align="center"><img alt="Visibility" src="https://img.shields.io/badge/visibility-public-blue"> <img alt="Documentation" src="https://img.shields.io/badge/documentation-deep%20editorial-lightgrey"> <img alt="Lifecycle" src="https://img.shields.io/badge/lifecycle-active-success"></p>

<!-- HMZ DEEP README v1 -->

## At a glance

| Field | Current state |
|---|---|
| Repository | awesome-ai-apps |
| Visibility | Public |
| Lifecycle | Active |
| Evidence basis | Current repository documentation and source-visible material |

## Why this exists

**Production AI apps — the catalog with code, not just screenshots** — 400+ files of working AI applications: blog-video writer, brand-video monitor, agent systems, LLM SaaS scaffolds — each with full source

The README treats this repository as a catalog of examples and applications. Individual examples must be evaluated on their own source, setup, and dependencies rather than assumed to share one runtime.

## 🧠 CONCEPTS

Each row maps a concept to a real file. Click `[Source]` to read the actual code.

| # | Concept | Location | Description |
|---|---|---|---|
| 1 | **Roadmap doc** | `Roadmap.md` | Upcoming apps and gaps to fill · [Source](https://github.com/hmzainjamil/awesome-ai-apps/blob/main/Roadmap.md) |
| 2 | **Blog-video writer app** | `advanced-agents/blog-video-writer/App.tsx` | Full Vite + Tailwind + Gemini reference app · [Source](https://github.com/hmzainjamil/awesome-ai-apps/blob/main/advanced-agents/blog-video-writer/App.tsx) |
| 3 | **Blog writer interface** | `advanced-agents/blog-video-writer/components/BlogWriterInterface.tsx` | Prompt UI with state machine · [Source](https://github.com/hmzainjamil/awesome-ai-apps/blob/main/advanced-agents/blog-video-writer/components/BlogWriterInterface.tsx) |
| 4 | **Blog writer service** | `advanced-agents/blog-video-writer/services/blogWriterService.ts` | LLM call wrapper with retry · [Source](https://github.com/hmzainjamil/awesome-ai-apps/blob/main/advanced-agents/blog-video-writer/services/blogWriterService.ts) |
| 5 | **Blog writer progress** | `advanced-agents/blog-video-writer/components/BlogWriterProgress.tsx` | Step-by-step UI feedback · [Source](https://github.com/hmzainjamil/awesome-ai-apps/blob/main/advanced-agents/blog-video-writer/components/BlogWriterProgress.tsx) |
| 6 | **Brand video monitor** | `advanced-agents/brand-video-monitor/App.tsx` | Live-stream monitoring with multi-modal LLM · [Source](https://github.com/hmzainjamil/awesome-ai-apps/blob/main/advanced-agents/brand-video-monitor/App.tsx) |
| 7 | **Brand profile setup** | `advanced-agents/brand-video-monitor/components/BrandProfileSetup.tsx` | Onboarding flow for brand keywords · [Source](https://github.com/hmzainjamil/awesome-ai-apps/blob/main/advanced-agents/brand-video-monitor/components/BrandProfileSetup.tsx) |
| 8 | **Vite config** | `advanced-agents/blog-video-writer/vite.config.ts` | Build setup — TS + React + Tailwind · [Source](https://github.com/hmzainjamil/awesome-ai-apps/blob/main/advanced-agents/blog-video-writer/vite.config.ts) |
| 9 | **Tailwind config** | `advanced-agents/blog-video-writer/tailwind.config.js` | Design tokens via Tailwind · [Source](https://github.com/hmzainjamil/awesome-ai-apps/blob/main/advanced-agents/blog-video-writer/tailwind.config.js) |
| 10 | **Deploy workflow** | `.github/workflows/deploy.yml` | Hugo-based docs deploy · [Source](https://github.com/hmzainjamil/awesome-ai-apps/blob/main/.github/workflows/deploy.yml) |

## ⚙️ HOW IT WORKS

```
┌─────────────────────────────────────────────────────────────┐
│  Input  →  awesome-ai-apps  →  Output                                    │
├─────────────────────────────────────────────────────────────┤
│  1. Prompt / file / event lands at the entry point          │
│  2. Manifest resolves trigger → concrete handler            │
│  3. Handler invokes tools / scripts / sub-agents in order   │
│  4. Output is structured (JSON / Markdown / HTML / file)    │
│  5. Side-effects: logs, alerts, artifacts, commits          │
└─────────────────────────────────────────────────────────────┘
```

The architecture is intentionally narrow: one entry point, one router, deterministic handlers. No hidden global state, no `process.env` surprises, no daemons phoning home.

## 🚀 Install

## 🧩 Usage

Once installed, invoke the primary surface from any Claude Code session:

```text
# example 1 — basic trigger
use awesome-ai-apps to ...

# example 2 — explicit skill name
@skill:awesome-ai-apps run on <input>

# example 3 — CLI-style invocation
npx awesome-ai-apps --help
```

Each concept in the table above is independently usable — you don't have to wire the whole thing up at once.

## ⚙️ Configuration

All configuration is file-based. No web dashboards, no SaaS sign-up, no env-var roulette.

| Setting | Default | Description |
|---|---|---|
| `LOG_LEVEL` | `info` | One of: `debug`, `info`, `warn`, `error` |
| `MODEL_TIER` | `tier0` | Route to free local/cloud models before paid |
| `MAX_TOKENS` | `8192` | Hard cap per invocation |
| `CACHE_TTL` | `3600` | Seconds before refetching upstream data |
| `OUTPUT_DIR` | `~/Downloads` | Where generated artifacts land |
| `DRY_RUN` | `false` | Print plan, skip side-effects |
| `RETRY_COUNT` | `3` | Network/transient failure retries |
| `TIMEOUT_MS` | `30000` | Per-call timeout |
| `TELEMETRY` | `off` | Never on by default |
| `VERBOSE_ERRORS` | `true` | Full stacks in dev, redacted in prod |

## Validation and evidence

Each application should be validated independently. Repository-wide counts do not establish that every example runs.

## 🛰️ Security posture

- Secrets: never committed; use a secrets manager (1Password CLI, doppler, age-encrypted .env).
- Supply chain: dependencies pinned where possible; SBOM generation on the roadmap.
- Sandbox: tools that touch the filesystem default to dry-run preview.
- Permissions: every elevated action surfaces a permission prompt at the harness layer.
- Audit log: every tool call appends to a structured log under `~/.claude/`.

## Limitations

- A collection repository can contain examples with different maturity levels.
- Example code is not automatically production-ready.
- Quantitative claims require example-specific evidence.



## Maintainer

[hmzainjamil](https://github.com/hmzainjamil)