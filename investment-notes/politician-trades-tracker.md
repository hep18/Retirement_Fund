# Politician Trades Tracker

Tracking congressional / political-figure stock disclosures as a **secondary signal** in the daily research workflow. Treated as one input among many — never the sole basis for a trade.

## Why track this

STOCK Act (2012) requires US Senators and Representatives to disclose any financial transaction within 45 days. Some politicians (notably the Pelosi household) have a documented multi-decade track record of outperforming the S&P, particularly on large-cap tech. Aggregator X accounts and websites surface these PTR filings as they hit the public record.

## Honest limitations

1. **45-day disclosure lag.** By the time a trade hits the public record, the move can be weeks old and partially priced in. Worst case: the politician has already exited by the time we see the entry.
2. **Selection bias in coverage.** Aggregator accounts highlight the eye-catching trades (large $ amounts, well-known names, sympathetic narratives), not necessarily the alpha-generating ones.
3. **Academic evidence is mixed.** Pelosi-household returns are real and outlier; broad-Congress portfolios are closer to market returns after fees.
4. **My direct access is limited.** All three X accounts the user named (@InTheAssembly, @QuiverQuant, @pelositracker) and the major aggregator websites (QuiverQuant, Capitol Trades, Unusual Whales, pelositracker.app) return HTTP 403 to my WebFetch tool. WebSearch gives me news articles *about* trades, which works but is itself lagged and incomplete.

## Workflow

Because of the access limitation, the daily workflow is:

1. **User surfaces notable trades.** If you see something on @InTheAssembly / @QuiverQuant / @pelositracker that looks interesting, paste the tweet text (or a screenshot description, or just the politician + ticker + buy/sell) into chat.
2. **I do the company-level research.** Same standard as other watchlist items: thesis, downside, time horizon, confidence, sourced from primary materials (SEC filings, company IR, wire services).
3. **I cross-check against our positions.** If a politician trade aligns with or contradicts what we already hold, that gets flagged in §8 of the daily note.
4. **I'll also do a best-effort web check.** Each day I'll WebSearch for recent congressional disclosures involving large-cap names we care about (AI, energy, defense, semis) and surface anything notable, with the caveat that this is news-article-derived, not direct from the PTR feed.

## Cross-reference with current holdings (as of 2026-05-14)

| Our position | Politician signal | Direction | Confidence in signal |
|---|---|---|---|
| NVDA (long, fractional) | Pelosi household has been a repeated buyer of NVDA shares and calls through 2025 and into early 2026. Most recent disclosed event: Jan 16, 2026 — 50 call options exercised at $80 strike, adding 5,000 shares. Source: Nasdaq.com / Motley Fool / pelositracker coverage (Feb 2026). | **Aligned (bullish)** | Medium — Pelosi posture is multi-quarter, not a fresh signal |
| NVDA (long, fractional) | Rep. Daniel Meuser disclosed a partial NVDA sale on Apr 14, 2026; he has been a consistent seller across 2026. Source: Benzinga, Yahoo Finance. | **Contradicts (bearish)** | Low — Meuser's selling track record has been a poor forward signal (per "missed 631% gain since 2022" framing) |
| XLE (long) | No specific congressional energy/oil disclosure signal found in May 2026 search. | N/A | — |
| RKLB (long) | No specific congressional RKLB / space / defense disclosure signal found. Defense procurement trades by senators on Armed Services committee would be the highest-value signal here, but none surfaced in today's search. | N/A | — |

**Net read on NVDA today:** Pelosi-aligned (mild positive); Meuser-counter (low weight). Doesn't change our 4/10 confidence on the NVDA position, but doesn't contradict it either.

## Trades log

Format: date logged | politician | ticker | direction | size | trade date | disclosure date | source | our take

| Logged | Politician | Ticker | Dir | Size | Trade Date | Disclosed | Source | Take |
|---|---|---|---|---|---|---|---|---|
| 2026-05-14 | N. Pelosi | NVDA | Buy (exercised calls) | ~5,000 sh equivalent | 2026-01-16 | 2026-01-23 | Nasdaq, Motley Fool (Feb 2026) | Aligns with our NVDA add today. Old by now. |
| 2026-05-14 | N. Pelosi | AB (AllianceBernstein) | Buy | $1M-$5M | Late Dec 2025 | 2026-01-23 | Search results | Dividend-oriented financial. Not on our radar; would Watch. |
| 2026-05-14 | Rep. D. Meuser | NVDA | Sell (partial) | $1K-$15K | ~Late March 2026 | 2026-04-14 | Benzinga | Counter signal but Meuser sell-track record is poor. |
| 2026-05-14 | Rep. J. Harman | RACE, BP, BTLCY, BCS | Buy | $1K-$15K each | 2026-04-20 | (filing date in May per search) | Capitol Trades via search | International / energy diversification. Not actionable for our $1k account; Watch BP. |
| 2026-05-14 | Rep. D. Taylor | (multiple incl. AVGO) | Mixed | $1K-$15K each | 2026-04-27 | 2026-05-07 | Capitol Trades via search | Spread small trades; no concentrated signal. |

## Open items

- **User to paste specific tweets / trades they want researched** from @InTheAssembly, @QuiverQuant, @pelositracker as they appear.
- Consider whether a paid API to a politician-trade data feed (Unusual Whales, QuiverQuant API) is worth it — fees on a $1,123 account are prohibitive, but worth revisiting if the account grows.
