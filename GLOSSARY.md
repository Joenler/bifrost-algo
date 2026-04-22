# GLOSSARY

Domain-term definitions shared by the C# and Python frameworks. Populated in Phase 11.

Terms that will be defined here:

- **DAH** — Day-Ahead auction (pre-round uniform-price clearing).
- **BRP** — Balance Responsible Party.
- **Aggregate-position imbalance** — the pricing model per ADR-0003.
- **Regime** — Calm / Trending / Volatile / Shock (internal code names; display labels deferred to Phase 11).
- **Gate** — the settlement transition; exchange rejects new orders once `RoundState=Gate`.
- **Cohort** — ForecastUpdate dispatch unit for per-team cohort-jittered fan-out (Phase 07).
