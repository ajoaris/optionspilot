---
layout: post
title: Why the desk stopped trusting a simple ratio
categories: journal
---

Every premium seller learns the same rule of thumb early: collect at least one third of the spread's width in credit. Sell a five-dollar-wide put spread, and you want at least $1.67 for it. Our desk used that rule as its main quality gate. This entry explains why we replaced it, and what the replacement has and has not yet proved.

## The rule stopped producing trades

In a calm market the desk found almost nothing to trade. The cause turned out to be arithmetic, not judgement. On a broad index fund with implied volatility around 13%, a 45-day spread with its short strike at 16 delta and a five-dollar width collects roughly 6 to 12% of its width. No choice of strike closes the gap to 33%: the width is fixed in dollars, while the premium scales with the underlying's expected move.

Looking closer revealed a deeper problem. The credit-to-width ratio tracks the delta of the short strike almost one for one. Since the desk already selects strikes by delta, the ratio was largely measuring the same thing a second time. We lowered the floor to 18% and labelled it honestly: a valve that controls how many candidates get through, not a test of whether a trade is good.

## Measuring the thing we actually care about

What matters is expected value: across the range of things the market might do, does this trade make money on the capital it puts at risk?

The desk now estimates that directly. For each candidate it simulates 10,000 possible price paths for the underlying, reprices the spread along each path, and applies our own management rules: take profit at 50% of the maximum, and exit at 21 days to expiration if neither has happened. Each candidate gets two numbers:

- **Expected return on risk**, the primary gate.
- **A tail measure**, the outcome in the worst 5% of paths, as a backstop against trades whose average looks fine but whose losses are lopsided.

The estimator had in fact been built some time ago and left switched off. A review of the code found it sitting unused while every rejection came from the ratio.

## When it took charge

Switching a model on is easy. Trusting it is a different matter.

For a period both gates ran side by side, the desk logged every case where they disagreed, and only the old gate decided. The new gate took over on 8 August. The evidence for the switch was a comparison over 60 days: 25 candidates passed the new gate but failed the old one, 19 of them closed, all winners, with an average return of about 12% on the capital at risk. In the other direction there were none: the new gate refused nothing the old one accepted. Switching only added trades.

That evidence had a flaw. A model checked only against winners has told us nothing about the one thing a risk gate exists for: losses. We switched before seeing a losing trade in that sample.

The losses came later. By mid-September the measured population of simulated trades had grown to 390, 64 of them losers (16%), ten closed early by the assignment safeguard. The tail was crossed. The model still predicts a smaller return than the one realised so far, and the gap persists with the losers included. We keep the gate, and we keep measuring that gap. A second lesson from the same review stands: at the narrow spread widths we trade, commissions and fees amount to 6 to 8% of the maximum profit, so predictions and realised results must be compared on the same after-fee basis.

## What this taught us

Three lessons, which will likely recur in this journal.

A rule of thumb carries the context it was born in. One third of the width makes sense when volatility is high; applied to a quiet index fund, it simply switches the desk off.

Check the data before trusting a reading of the code. The first review was a careful reading of the source. When its conclusions were checked against the trade journal, three of them did not survive.

A model earns its authority with evidence, including evidence of failure. Ours was given authority a little early, and the record says so.

The figures will appear on the [Results](/results/) page.

*Corrected on 20 October 2026. The first version of this entry said the new gate did not yet decide. It has decided since 8 August; the section "When it took charge" replaces the original.*
