+++
title = "Algorithm Rules"
author = ["Stefan Lendl"]
draft = false
+++

:ID:       3d2f35ed-3bb2-49c2-80be-209caf62b56c


## Algorithm Rules {#algorithm-rules}

The algorithm rules describe how the signals of individual [indicators]({{< relref "Indicator" >}}) are
combined to make a trading decision.

The rules describe a signaling indicator and multiple filter indicators. The
signaling indicator gives a signal and if the filter indicators agree to this
signal, a new trade may be opened.

Indicators at the **confirmation**, **baseline** and **continuation** function act as signaling
indicators. All other indicators act as a filter. Baseline is also a filter for
a confirmation signal and vice-versa.


### Confirmation Signal {#confirmation-signal}

If the confirmation indicator (C1) produces a [signal]({{< relref "Signal" >}}) the [sides]({{< relref "20200820171402-side" >}})
of C2, E, B and V need to be the same direction as the signal.


#### One Candle Rule {#one-candle-rule}

If at the moment of the C1 signal the filter indicators do not comply, the sides
of the filter indicators are again checked one candle / bar later and if they
comply then, the trade is taken.


#### <span class="org-todo todo TODO">TODO</span> Confirmation State Machine {#confirmation-state-machine}


### Baseline Signal {#baseline-signal}

If the price crosses the baseline (B) and closes on the other side than it closed
the previous candle this is a baseline signal. The sides of C1, C2, E and V are checked.
On the sequential candles the baseline is still treated as indicating a signal.


#### ATR Channel {#atr-channel}

If price is **not** within the baseline ATR channel (\\(B \pm ATR\\)), price has gone
too far and no trades shall be taken.


#### Pullback {#pullback}

If price crosses the baseline with a long candle and closes outside the ATR
channel a potential pullback can be expected. A pullback occurs if price closes
within the ATR channel on the next candle and is treated as a baseline signal.


#### Bridge Too Far {#bridge-too-far}

The limit number of candles \\(x\\) after the baseline signal where the baseline is
treated as indicating a signal.

For the daily chart VP gave \\(x=7\\) as the bridge too far.


#### <span class="org-todo todo TODO">TODO</span> Baseline State Machine {#baseline-state-machine}


### Continuation Signal {#continuation-signal}

If the trade was closed out but the trend is still going there may be continuation
signal as explained in [MACD Indicator Strategy](https://nononsenseforex.com/indicators/macd-indicator-strategy/).


#### <span class="org-todo todo TODO">TODO</span> Continuation State Machine {#continuation-state-machine}


### Combined Signal {#combined-signal}
