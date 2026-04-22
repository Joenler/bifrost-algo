# RULES

Operational rules every team must understand: guards, scoring formula, imbalance
mechanics, and the distinction between bypassable config and non-bypassable invariants.
Populated in Phase 11.

Sections that will land here:

- Pre-trade guards (per ADR-0004 — OTR, max-open-orders, max-notional, position cap, self-trade protection, message-rate limit, **no** price-sanity guard).
- Scoring formula (`total = trade_pnl + imbalance_pnl + fees − otr_penalty`).
- Imbalance settlement mechanics (per ADR-0003 — aggregate-position model).
- Non-bypassable rules vs configurable parameters.
- Round lifecycle states (`IterationOpen → AuctionOpen → AuctionClosed → RoundOpen → Gate → Settled → IterationOpen`).
