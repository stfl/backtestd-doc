+++
title = "Parameter Optimization"
author = ["Stefan Lendl"]
draft = false
+++

[Developing & Backtesting Systematic Trading Strategies (pdf)](/ox-hugo/strat_dev_process.pdf)

Peterson, Brian. (2017). Developing & Backtesting Systematic Trading Strategies.

> Parameter optimization is important for indicators, signals, rules, and
> complete trading systems. Care needs to be taken to do this as safely as
> possible. That care needs to start with clearly defined objectives, as has
> already been stated. The goal of parameter optimization shouldbe to locate a
> parameter combination that most closely matches thehypotheses and objectives.
> To avoid overfitting, it is also critical toavoid outliers, looking for stable
> regions of both in and out of sampleperformance. (Tomasini and Jaekle2009,
> pp.49--56)When a parameter or set of parameters is robust, it will have a
> fewkey properties:

-   **small parameter changes lead to small changes in P&L and objective
    expectations**
-   out of sample deterioration is not large, on average (see walkforward
    optimization)
-   parameter choices have a sound theoretical or economic basis
-   parameter variation should produce correlated differences in multiple
    objectives
