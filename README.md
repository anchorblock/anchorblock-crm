# Anchorblock CRM

Anchorblock's CRM, built on [Twenty](https://github.com/twentyhq/twenty), the open-source CRM. This repository is a trimmed fork that keeps only what the deployed app needs.

## Packages

| Package | Purpose |
|---|---|
| `twenty-front` | React web app |
| `twenty-server` | NestJS API and background worker |
| `twenty-shared`, `twenty-ui`, `twenty-emails` | Shared code, UI library, email templates |
| `twenty-sdk`, `twenty-client-sdk`, `twenty-front-component-renderer` | Application runtime used by front and server |
| `twenty-oxlint-rules` | Lint rules |
| `twenty-docker` | Container entrypoint used by `Dockerfile.vercel` |
| `twenty-utils` | Local dev environment setup |
| `twenty-e2e-testing` | Playwright end-to-end tests |
| `twenty-docs/ui` | UI component docs read by the server's AI UI-docs tests |

Upstream's docs site, marketing website, marketplace apps, CLI, Zapier integration, desktop companion and agent skills are not included.

## Local development

```bash
bash packages/twenty-utils/setup-dev-env.sh   # Postgres, Redis and database init
yarn start                                    # front, server and worker
```

See [CLAUDE.md](./CLAUDE.md) for code conventions and the full command list.

## Deployment

The app deploys to Vercel as a container web service plus a worker daemon (`vercel.json`, `Dockerfile.vercel`), backed by Supabase Postgres.

## License

AGPLv3, inherited from Twenty. See [LICENSE](./LICENSE).
