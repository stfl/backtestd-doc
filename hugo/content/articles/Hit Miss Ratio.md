+++
title = "Hit Miss Ratio"
author = ["Stefan Lendl"]
draft = false
+++

## Definition {#definition}

The hit miss ratio [Metric]({{< relref "Metrics" >}}) is defined by [VP]({{< relref "VP" >}}) in
[Backtesting
Step-by-step](https://nononsenseforex.com/forex-q-and-a-podcast/forex-backtesting-step-by-step/) as _win-rate_.

This metric indicates if right after the entry signal price moves in our
direction before it moves the other way.

We use the terminology hit/miss instead of win/loss.

> Here is what determines a win [hit] or a loss [miss], listen up.
>
> 1.  – Start from today, and go back in time until you see your indicator give a
>     buy or sell signal.
> 2.  – Find the value of the ATR at the time the buy/sell signal was given. We do
>     not care what the ATR was at any other point in time. We only care about what
>     it was when we got the signal.
> 3.  – Then find out which happened first. Did price end up hitting the value of
>     the ATR first, or did it hit the value of 1.5 x ATR int he opposite direction
>     first?
>
> For example: If the ATR at the time of the signal was 80 pips — which happened
> first? Did the trade make you 80 pips of profit, or did it lose you 120 pips?
> Which occurred first?
>
> If the profit happened first, it’s officially a WIN. If the loss happened first,
> it’s officially a LOSS.

In short terms this is the ratio of [TP]({{< relref "20200820135056-tp" >}}) vs SL hits \\( \frac{TP}{SL} \\)

The TP is set at a distance of \\(1\*ATR\\) whereas the SL is set at \\(1.5\*ATR\\). With
this distances and the assumption that the probaility of the price ot move up or
down is approximately identical the
[random indicator]({{< relref "20200820135757-random_indicator" >}}) would score
\(1 - \frac{1 ATR}{2.5 ATR} = 0.6\).


## Implications {#implications}

When using the metric for automatic optimization it favours configurations with
few trades. A config with only a single entry signal witch is a hit results in a hit/miss ratio of 1.
