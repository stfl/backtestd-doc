+++
title = "Analyzing Results"
author = ["Stefan Lendl"]
draft = false
+++

When backtesting indicators or indicator sets there is a significant likelihood
of [curve fitting](https://en.wikipedia.org/wiki/Curve%5Ffitting) which gives good results for the specific backtested period but
would not give good results in forward testing. This is also called
over-optimization.


## Filtering Over-Optimization {#filtering-over-optimization}

[Parameter Optimization]({{< relref "Parameter Optimization" >}}) describes that if
the value of a [Continuous Input]({{< relref "Input Parameters#continuous-input" >}}) changes, the result value
must change proportionally to the input change.


### Assumtion: {#assumtion}

based on [Parameter Optimization]({{< relref "Parameter Optimization" >}})

If the value of a continuous input changes by a single step but the result
changes significantly, the results can be considered random and must be filtered.

_What is significant?_
