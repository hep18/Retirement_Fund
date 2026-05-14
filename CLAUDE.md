# Investment Research Workflow — Template Notes

This file captures persistent template / behavior changes the user has requested across sessions. It supplements the workflow described in the initial system prompt.

## Daily note section structure (as of 2026-05-14)

The daily note format has been extended from 7 sections to 8:

1. Newsletter Summary
2. Key Market Themes
3. Company and Sector Watchlist
4. Deeper Market Research
5. Trend Comparison
6. Portfolio Recommendation
7. **Low-Risk Action Summary (Conservative Path)** — defaults to Hold / Watch, respects the workflow's "moderate risk" tolerance, follows the hard rule against newsletter-driven trades.
8. **Aggressive Action Summary (Higher-Risk Path)** — thinner evidence threshold, willingness to act on macro thesis, explicit speculative framing. Hard rules still apply: every idea has thesis (sourced), downside, time horizon, confidence. Includes ideas considered and rejected. Includes a combined-execution summary so the user sees what the aggressive book looks like as a whole.

Both §7 and §8 should include an action table. §8 must include explicit speculative-disclaimer framing at the top.

## Hard rules that apply to BOTH §7 and §8

- Cite every claim that isn't common knowledge. "Source:" for facts; "Inference:" for reasoning.
- Mark unverified prices / numbers as *unverified*.
- Never recommend a trade based on the newsletter alone — even in §8, the thesis must be backed by primary or wire-service sources independent of the Brew.
- Size suggestions for the actual account balance, not a hypothetical larger one.
- Account for trading frictions on small trims.

## Politician / congressional trades as a secondary signal

Each day, also surface politician trading signals as a Watch input:

- **Files:** `/investment-notes/politician-trades-tracker.md` is the running log. Append new entries; cross-reference current holdings in the daily note.
- **Primary X accounts the user follows:** @InTheAssembly, @QuiverQuant, @pelositracker.
- **Direct access limitation:** X profiles and the major aggregator sites (QuiverQuant, Capitol Trades, Unusual Whales, pelositracker.app) return 403 to WebFetch. Workaround: (a) WebSearch for recent congressional trade news on names in our book + names in today's newsletter, (b) user pastes specific tweets / trades they want researched.
- **Treatment:** Politician trades are a secondary signal, never the sole basis for a trade. Apply the same hard rules: thesis, downside, horizon, confidence. Note the 45-day disclosure lag explicitly.
- **In the daily note:** Cross-reference current holdings vs. recent disclosed trades in §4 (Deeper Research) or §8 (Aggressive). Surface contradictions and alignments. Don't auto-mirror trades.

## Account risk profile (as of 2026-05-14)

The user has explicitly stated this is their **designated risky / speculative account**. They hold separate, less-risky accounts elsewhere for stable / retirement capital.

Implications for the workflow:
- **§8 (Aggressive) is the primary recommendation path for this account**, not the alternate path. §7 (Low-Risk) is retained as a counterfactual baseline so the user can see the conservative read, but recommendations should lead with §8.
- **Stop flagging high single-name concentration as if it were an error.** A risk-account is *expected* to run concentrated. Do flag concentration when it crosses a thesis-driven threshold (e.g., one position > 70% of book), but frame it as a *position-management* observation, not a *risk-tolerance* mismatch.
- The "moderate risk" language in the original workflow system prompt is overridden by this account-specific instruction. Treat risk tolerance as **high / speculative** for this account specifically.
- Hard rules above still apply — sourcing, thesis structure, downside, horizon, confidence. High risk tolerance is not permission to skip diligence.
- Continue to default to Hold/Watch when evidence is genuinely thin. Risk tolerance affects *position sizing and idea threshold*, not the bar for evidence.
