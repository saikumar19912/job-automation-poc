# Contributing

Thanks for your interest in contributing to job-automation-poc!

Please follow these guidelines to make the contribution process smooth.

## How to contribute
1. Open an issue to discuss major changes or features before work begins.
2. Fork the repository and create a branch: `feat/your-feature` or `fix/your-bug`.
3. Make changes and include tests or sample data when relevant.
4. Keep changes focused and add a clear commit message.
5. Open a Pull Request against `main` with a description of what changed and why.

## Importing the n8n workflow
- Open n8n (self-hosted or cloud).
- Workflows → Import → upload `workflows/n8n-job-ingestion-poc.json`.
- Configure credentials via the n8n credentials UI (do not commit secrets).

## Local validation
- Validate JSON files with `jq`:
  - `jq . workflows/n8n-job-ingestion-poc.json`
- Update `docs/data-schema.md` when changing any output columns or field types.

## Code of conduct
Please be respectful — follow common open-source community norms.

## Do not
- Commit any credentials or secrets (API keys, OAuth tokens, service account JSON).
- Include large binary files in the repo; prefer external storage if needed.