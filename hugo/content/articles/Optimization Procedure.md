+++
title = "Optimization Procedure"
author = ["Stefan Lendl"]
draft = false
+++

The optimization procedure in this system defines the process of finding a
profitable configuration for the system according to the given [algortihm rules]({{< relref "Algorithm Rules" >}}).


## <span class="org-todo todo TODO">TODO</span> Backtesting in Metatrader 5 {#backtesting-in-metatrader-5}


## New Indicators {#new-indicators}

The optimization starts with [adding]({{< relref "Adding New Indicators" >}}) and [testing new indicators]({{< relref "Testing New Indicators" >}}) to calculate the
[metric]({{< relref "Metrics" >}}) for a range of [Input Parameters]({{< relref "Input Parameters" >}}). In order to filter [(reduce)]({{< relref "Reducing the result set" >}}) the result
for further processing we [analyze the results]({{< relref "Analyzing Results" >}}). The resulting configurations is
referred to as [Sliced Indicator Set]({{< relref "Sliced Indicator Set" >}}).


## Continuous Optimization {#continuous-optimization}

From the previously gathered sliced indi set configs multiple candidates are
  [selected]({{< relref "Indicator Selection" >}}) - based on a
  [metric]({{< relref "Metrics" >}}) - and [combined]({{< relref "Combination of Indicators#combining" >}}) to breed a new indi set for further
  backtesting. This process runs automatically and is based on principales of a
  [genetic algorithm](https://en.wikipedia.org/wiki/Genetic%5Falgorithm).
  Progressively the the number of assigned functions in the indi set will grow
  until all functions are assigned.


## Forward Testing {#forward-testing}

After we find a suitable indicator set with all functions assigned we select a
[Input Parameters]({{< relref "Input Parameters#Concrete Indicator Set" >}}) and forward test the configuration for a certain period
of time until we are conviced that the configuration is acceptable. Forward
testing is performed on a demo account of a broker of choice.


## Building a Track Record {#building-a-track-record}

In order to monetize the signals from the algorithm it is important to generate
a record of actual trades either on a demo account or a real-money account. The
results from forward testing may be used as track record as well.
