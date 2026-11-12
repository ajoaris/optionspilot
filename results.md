---
layout: page
title: Results
permalink: /results/
---

Results are reported as percentages of capital at risk. Account sizes are not published.

*Figures as of 12 November 2026.*

## Method

- **Return on capital at risk**: total profit or loss of the closed trades divided by the total of their maximum possible losses.
- **Including open positions**: the same ratio with positions still open added at their latest mark. A book can look profitable on closed trades alone while its losing positions are still open; this column corrects for that.
- **Win rate**: share of closed trades that ended in profit.
- **Average days held**: from entry to close.
- **Largest drawdown**: the deepest peak-to-trough decline over the period, as a percentage of the account value the book is simulated on.

Simulated trades, which the system proposes but does not execute, are reported separately from live trades. Simulated results are for one contract per trade, net of commissions and of an allowance for slippage on exits.

## Simulated books

Each book applies a different policy to the same candidates and the same account value. They are described in the journal entry [Four books, one honest scoreboard](/journal/2026/11/four-books-one-scoreboard/).

| Book | Since | Closed trades | Win rate | Return on capital at risk | Including open positions | Average days held | Largest drawdown |
|---|---|---|---|---|---|---|---|
| A, the baseline | 9 September | 20 | 50% | −18.9% | −15.9% | 17 | 21.6% |
| B, rules decide | 29 September | 23 | 78% | −3.6% | −5.8% | 11 | 11.1% |
| C, with a news analyst | 5 October | 11 | 91% | +4.8% | −2.7% | 8 | 5.4% |
| D, the model decides | 20 October | 8 | 100% | +11.1% | −0.3% | 7 | 5.5% |
| E, a third of the width | 12 November | 0 | n/a | n/a | n/a | n/a | n/a |

Three cautions apply to this table.

**The books did not live through the same market.** They started at different dates, and the two with positive figures started last. The ranking mostly reflects the calendar.

**No book is positive once open positions are counted.** The sixth column is the one to read.

**The samples are small.** Eight or eleven closed trades say very little.

Book B was retired on 11 November: once book A adopted its policy, the two no longer differed. Its open positions run to their exit. Book E had opened one position and closed none at the date of these figures.

### By structure

Return on capital at risk on closed trades, with the number of winners out of trades closed.

| Structure | Book A | Book B | Book C | Book D |
|---|---|---|---|---|
| Bull put spread | −24.5% (6 of 16) | −8.8% (11 of 15) | −1.6% (4 of 5) | +9.9% (1 of 1) |
| Bear call spread | +12.7% (4 of 4) | +9.2% (7 of 8) | +11.5% (6 of 6) | +11.3% (7 of 7) |

The books often hold the same trade on the same day, so these columns overlap and must not be added together.

## Live trades

Real trades placed between May and August 2026; the last one closed on 8 September. No live trade has been opened since.

| Structure | Closed trades | Win rate | Return on capital at risk | Average days held |
|---|---|---|---|---|
| Bull put spread | 15 | 87% | +14.5% | 10.5 |
| Bear call spread | 11 | 27% | −2.5% | 1.0 |
| Iron condor | 3 | 0% | −52.8% | 2.0 |
| **All** | **29** | **55%** | **+4.3%** | **6.0** |

Twelve of these trades, ten of them bear call spreads, were closed on the day they were opened. That was an error in the algorithm in its first days, not a decision, and it weighs on the bear call figures.

**Largest drawdown: not measured.** The account value over the period was not recorded alongside the trades.

These trades were taken with wider spreads and richer credits than the simulated books use today, so the two sections are not directly comparable.
