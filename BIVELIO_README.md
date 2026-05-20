# BiVelio Orchestrator — mirror notice

> **This repository is a managed mirror of [paperclipai/paperclip](https://github.com/paperclipai/paperclip)** maintained by Chronos Technology / BiVelio for self-host autonomy.

## Purpose

BiVelio uses PaperClip as the engine behind its **Orchestrator** module (PRO plan) to give organizations the ability to coordinate AI agents (Claude Code, Codex, OpenClaw) with org charts, budgets, governance, and skills — all surfaced inside `app.bivelio.com` with native BiVelio UI.

This mirror exists to guarantee that BiVelio can keep operating even if the upstream repository ever becomes unavailable.

## License

PaperClip is **MIT licensed** — see `LICENSE`. This mirror preserves the original license and copyright notice. All credit goes to the [Paperclip AI team](https://github.com/paperclipai).

## Sync policy

- `master` branch is auto-synced from `upstream/master` every Monday at 06:00 UTC by `.github/workflows/sync-upstream.yml`
- BiVelio does **NOT** modify the engine code. The only files BiVelio owns in this repo are:
  - `.github/workflows/sync-upstream.yml` — the sync workflow itself
  - `.github/workflows/build-image.yml` — the Docker image build workflow
  - `BIVELIO_README.md` — this file
- Docker images are built on every push to `master` and on version tags, published to `ghcr.io/chronos-technology/orchestrator-engine`

## Do not push directly

If you need to change upstream behaviour, **open a PR against `paperclipai/paperclip` first**. Direct commits to this mirror will be overwritten by the next sync run.

## Production deployment

The BiVelio Orchestrator self-host runs Docker containers using pinned tags (NOT `:latest`):
- `orchestrator-test` → `ghcr.io/chronos-technology/orchestrator-engine:v0.1.0` (or pinned tag)
- `orchestrator-prod` → `ghcr.io/chronos-technology/orchestrator-engine:v0.1.0` (or pinned tag)

Deploy configuration lives in the main BiVelio monorepo under `services/paperclip/`.

## Contact

Questions: `team@c5s.xyz`
