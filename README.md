# bifrost-algo

Team-facing strategy frameworks for **BIFROST** — the LAN intraday-power-trading hackathon.

Each language subdirectory is an independent starter kit. Pick the one that matches your
strategy implementation language; clone, edit, `docker compose up` against the central
machine's gateway. The C# and Python frameworks are API-compatible — identical `IExecutionStrategy`
shape, identical SDK methods, identical TWAP baseline behavior on the same scenario seed.

## Quick start

Pick your language:

- **C# team?** `cd csharp && cat README.md` (Phase 08 lands the SDK + TWAP baseline here.)
- **Python team?** `cd python && cat README.md` (Phase 09 lands the SDK + TWAP baseline here.)

Both subdirs will expose a `docker compose up` UX starting in Phase 08 / Phase 09 respectively.

## Layout

| Path                  | What lives here                                                                |
|-----------------------|---------------------------------------------------------------------------------|
| `csharp/`             | C# SDK (`Bifrost.Sdk` NuGet) + TWAP baseline + Dockerfile + local dashboard. Phase 08 lands here. |
| `python/`             | Python SDK (`bifrost_sdk` pip) + TWAP baseline + Dockerfile + local dashboard. Phase 09 lands here. |
| `GLOSSARY.md`         | Shared domain terms (DAH, BRP, aggregate-position imbalance, regime, gate, cohort). Phase 11 fills. |
| `RULES.md`            | Shared rules (guards, scoring, imbalance mechanics, bypassable vs non-bypassable). Phase 11 fills. |
| `.github/workflows/`  | CI — markdownlint + link-check on push; Phase 08+ extends with per-language matrix slots. |
| `LICENSE`             | MIT.                                                                            |

## Connecting to the central machine

The central machine runs `bifrost-exchange` via `docker compose up`. It exposes a gRPC
strategy gateway on the LAN. Your strategy's Docker container connects outbound to that
gateway. LAN-only; no TLS; no auth beyond the team name you register with.

See the central-machine repo: [`bifrost-exchange`](https://github.com/Joenler/bifrost-exchange).

## Architecture decisions

The BIFROST program keeps its architecture decision records in the organizer-internal
`bifrost-program/` planning hub (kept local and not published to GitHub). The links
below resolve when this repo and `bifrost-program/` are cloned as siblings under the
same parent directory — the documented organizer workstation setup. Participants
cloning only `bifrost-algo` will not resolve these links; ADR content is
organizer-authored and not required reading to compete.

- [`ADR-0002` — gRPC Strategy Gateway](../bifrost-program/ADRs/ADR-0002-grpc-strategy-gateway.md) — the wire your SDK speaks.
- [`ADR-0003` — Aggregate-position imbalance pricing](../bifrost-program/ADRs/ADR-0003-imbalance-pricing-model.md) — how your position settles at gate.
- [`ADR-0004` — Fair-play guards](../bifrost-program/ADRs/ADR-0004-fair-play-guards.md) — what the gateway rejects.
- [`ADR-0005` — Command-driven MC console](../bifrost-program/ADRs/ADR-0005-mc-console-command-driven.md) — how rounds progress.
- [`ADR-0006` — Two-code-repo layout](../bifrost-program/ADRs/ADR-0006-two-code-repo-layout.md) — supersedes ADR-0001; explains why this repo exists alongside `bifrost-exchange`.

## License

MIT — see [`LICENSE`](./LICENSE).
