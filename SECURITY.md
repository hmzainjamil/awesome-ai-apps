# Security and example review

This repository contains application examples with independent dependencies and data flows. Review each project separately before installing or running it.

## API keys and browser applications

A Vite variable exposed through `import.meta.env` can be included in client-side code. The Blog Video Writer reads `VITE_GOOGLE_API_KEY` in its browser application. Do not treat a Vite-prefixed API key as a server-side secret. Use a restricted development credential, rotate exposed keys, and route sensitive requests through a server-side component you control.

## Before running an example

- Read the example README, source, package scripts, and dependency manifest.
- Identify model providers, data uploads, network calls, and generated outputs.
- Use synthetic or non-sensitive data until the flow is understood.
- Check current provider terms and privacy behavior.
- Do not run production workflows or supply customer data without appropriate review.

## Reporting

Do not post secrets, personal data, or exploit instructions in public issues. Use GitHub private vulnerability reporting if enabled, or contact the maintainer through a private channel listed on their GitHub profile. Include the affected path and safe reproduction details.

This guidance is not a security audit of the individual examples.
