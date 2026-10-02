# Awesome AI Apps

A collection of AI application examples and project folders. Each example has its own code, dependencies, configuration, and maturity. This repository does not expose a single shared install command or runtime.

The README highlights two independently structured Vite and React examples. It does not claim that every application in the repository is complete, runnable, production-ready, or maintained.

## Start with these examples

| Example | What the checked source shows | Entry points |
|---|---|---|
| Blog Video Writer | React interface and service code using the Google Generative AI SDK; reads `VITE_GOOGLE_API_KEY` and requests Gemini 1.5 Flash | [App](advanced-agents/blog-video-writer/App.tsx), [service](advanced-agents/blog-video-writer/services/blogWriterService.ts), [README](advanced-agents/blog-video-writer/README.md) |
| Brand Video Monitor | React flow for brand profile, configuration, video upload, progress, and results | [App](advanced-agents/brand-video-monitor/App.tsx), [README](advanced-agents/brand-video-monitor/README.md) |

Each example has its own `package.json`; review that folder's README and scripts before installing. For example, the Blog Video Writer declares `dev`, `build`, `lint`, and `preview` scripts. This does not establish that those commands currently pass.

The repository also has a [roadmap](Roadmap.md) and a [GitHub Pages workflow](.github/workflows/deploy.yml). The roadmap describes planned scope and goals; it is not evidence that listed projects exist or meet the stated maturity.

## Running an individual example

Start in that example's folder and follow its README. Before entering API keys or sample data:

1. Inspect the source, package scripts, and dependency versions.
2. Use a dedicated development key with suitable limits.
3. Check whether data is sent to a remote model or service.
4. Run locally with synthetic data first.
5. Build or lint only the selected example using its declared scripts.

Do not copy secrets into committed files. For Vite apps, variables prefixed for client-side exposure can become available in the browser bundle; use only credentials intended for client-side use or move sensitive calls behind a server you control.

## Scope and status

This is a set of example projects, not a unified product. No repository-wide application count or test result is asserted here. No example is represented as production-ready without current, example-specific validation.

The GitHub Pages workflow builds a Hugo site from the repository. Individual examples use their own toolchains. See each folder's documentation for its requirements.

## Security

See [SECURITY.md](SECURITY.md) for API-key, external-service, and example-review guidance.

