---
layout: post
title: Four books, one honest scoreboard
categories: journal
---

Since the last entry the desk has run four simulated books side by side, each applying a different policy to the same candidates and the same account value. This entry reports where they stand, what the comparison can and cannot say, and three changes that follow from it. The short version: none of the books makes money yet, and we now think we know why.

## What the books are

All four are simulated. The desk has placed no live trade since August, and nothing below involved real money. Each book takes one contract per trade, and its results are net of commissions and of an allowance for slippage on exits.

- **Book A** is the pipeline as it runs. Until October the model made the final selection; since then the rules decide and the model only advises.
- **Book B** was the same pipeline with the rules deciding from the start.
- **Book C** adds a model-driven analyst that reads the news around each candidate.
- **Book D** is the only place where the model decides, within hard limits it cannot override.

## The scoreboard

As of 9 November, on closed trades:

| Book | Since | Closed trades | Win rate | Return on capital at risk |
|---|---|---|---|---|
| A | 9 September | 20 | 50% | −18.9% |
| B | 29 September | 22 | 77% | −4.2% |
| C | 5 October | 11 | 91% | +4.8% |
| D | 20 October | 8 | 100% | +11.1% |

Read from top to bottom, this looks like a ranking. It is mostly a calendar. Once the positions still open are marked to market, every book is below zero. And the two books that look best are the two that started last, after a stretch in September and October that was hard on one structure in particular.

That structure is the bull put spread. In the two older books it lost money: 6 winners out of 16 in book A, 11 out of 15 in book B. The bear call spread, the same trade on the other side of the market, was profitable in every book and lost once in all of them combined. The younger books hold mostly bear calls, opened in a market that had already turned. On the days when two books saw the same candidate, they usually took the same trade and got the same result.

So the comparison says less about who selects better than it appears to. Over equal periods a gap remains in favour of the newer books, but it rests on a handful of trades, and most of it comes from avoiding one or two losers.

## The arithmetic that matters

One figure is the same in all four books, and it explains more than the differences between them. The average winning trade earns about one fifth of what the average losing trade costs.

With that ratio, a book needs to win roughly five trades out of six, about 83%, simply to break even. Two books are above that line, on 11 and 8 closed trades. That is not evidence; it is a good month.

The ratio comes from how much credit each trade collects. Across more than a thousand simulated trades since mid-September, the median credit was 16% of the spread's width. The losses, when they come, arrive at the 21-day exit or at the safeguard against early assignment, and they are several times that size.

## The ratio returns, in a different role

The entry of 19 October explained why the desk stopped using "collect one third of the width" as a quality gate. That reasoning stands. But the same entry contained a sentence whose consequence we had not drawn: the credit-to-width ratio tracks the delta of the short strike almost one for one.

If that is true, a third of the width is not something to filter for after the trade is built. It is something to build towards. The method we follow fixes the outcome, a credit of one third and therefore a risk of two thirds, and lets the strike and the width adjust to each underlying.

Measuring our own trades showed how far we were from that. The desk placed its short strike at the market's expected move, which we believed corresponded to about 16 delta. Measured on the trades themselves, it was 21 delta. And at 21 delta the credit is 16% of the width, exactly what the books collected. A third of the width only appears with the short strike near 35 to 40 delta.

There is a cost, and it is the open question. Selling closer to the money lowers the probability of success. On our past candidates, only 2% offered both a third of the width and at least a 60% probability of reaching half the maximum profit before our 21-day exit. Our probability is stricter than the figure usually quoted, which runs to expiration, so the two are not directly comparable. Even so, the tension is real.

A fifth book now tests this directly. Book E is book A with one difference: each trade is built to collect a third of the width, with that 60% floor. It will probably stay thin at first. A measurement grid records, for every candidate, what each combination of strike and width would have given, so that the floor can be chosen on figures.

## Fixing the referee

Each book has a criterion for being judged against book A, written down before the book started. The criteria themselves are sound: realised result plus open positions, same period, same account. The rule deciding *when* a book could be judged was not.

It waited for a number of positions to reach the 21-day exit. A trade that takes its profit early did not count. Since nearly all winners leave at the profit target, the rule counted mostly losers, and a book that kept winning could never be evaluated. Book D had closed eight trades, all winners, and stood at zero out of the thirty required.

We are changing the rule to count every closed position, and setting the same threshold of thirty for every book. For two of the books this amends a pre-committed criterion in mid-course. We would rather say so than leave a criterion in place that cannot return a verdict.

Book B is retired. Once book A adopted its policy, the two no longer differed in anything we could measure, and a book that tests nothing is only noise on the scoreboard.

## What this taught us

A comparison between books is first a comparison between periods. Before asking which policy is better, check that they lived through the same market.

Look for the number that is the same everywhere. The differences between the books drew the attention; the payoff ratio they share was the finding.

Measure what the system does, not what the code says it does. A comment in the source said 16 delta. The trades said 21.

A rule for judging deserves the same scrutiny as the thing judged. Ours could not have declared a winner, and no one had noticed, because it had never been asked to.

The next entry will report what the grid and book E show.
