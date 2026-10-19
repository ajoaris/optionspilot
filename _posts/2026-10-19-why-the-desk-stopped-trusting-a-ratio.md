---
layout: post
title: Why the desk stopped trusting a simple ratio
categories: journal
---

Every premium seller learns the same rule of thumb early: collect at least one third of the spread's width in credit. Sell a five-dollar-wide put spread, and you want at least $1.67 for it. Our desk used that rule as its main quality gate. This entry explains why we are replacing it, and why the replacement is not yet allowed to make decisions.

## The rule stopped producing trades

In a calm market the desk found almost nothing to trade. The cause turned out to be arithmetic, not judgement. On a broad index fund with implied volatility around 13%, a 45-day spread with its short strike at 16 delta and a five-dollar width collects roughly 6 to 12% of its width. No choice of strike closes the gap to 33%: the width is fixed in dollars, while the premium scales with the underlying's expected move.

Looking closer revealed a deeper problem. The credit-to-width ratio tracks the delta of the short strike almost one for one. Since the desk already selects strikes by delta, the ratio was largely measuring the same thing a second time. We lowered the floor to 18% and labelled it honestly: a valve that controls how many candidates get through, not a test of whether a trade is good.

## Measuring the thing we actually care about

What matters is expected value: across the range of things the market might do, does this trade make money on the capital it puts at risk?

The desk now estimates that directly. For each candidate it simulates 10,000 possible price paths for the underlying, reprices the spread along each path, and applies our own management rules: take profit at 50% of the maximum, and exit at 21 days to expiration if neither has happened. Each candidate gets two numbers:

- **Expected return on risk**, the primary gate.
- **A tail measure**, the outcome in the worst 5% of paths, as a backstop against trades whose average looks fine but whose losses are lopsided.

The estimator had in fact been built some time ago and left switched off. A review of the code found it sitting unused while every rejection came from the ratio.

## Why it is not in charge yet

Switching a model on is easy. Trusting it is a different matter.

Both gates now run side by side. The desk logs every case where they disagree, and only the old gate decides. When we first compared predictions with outcomes, the 16 closed trades in the sample were all winners, and the model's predictions were drifting away from the realised results. A model checked only against winners has told us nothing about the one thing a risk gate exists for: losses.

So the promotion rule is explicit. The new gate takes over only once at least 15 trades can be fully reconstructed from the record, and at least one of them is a realised loser. A second condition came out of the same review: at the narrower spread widths we now trade, commissions and fees amount to 6 to 8% of the maximum profit. Predictions and realised results must be compared on the same after-fee basis, or the calibration will chase a bias of several points.

## What this taught us

Three lessons, which will likely recur in this journal.

A rule of thumb carries the context it was born in. One third of the width makes sense when volatility is high; applied to a quiet index fund, it simply switches the desk off.

Check the data before trusting a reading of the code. The first review was a careful reading of the source. When its conclusions were checked against the trade journal, three of them did not survive.

A model earns its authority with evidence, including evidence of failure. Until then, it watches.

When the new gate takes over, or fails to, the figures will appear on the [Results](/results/) page.
