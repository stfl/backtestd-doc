+++
title = "Indicators"
author = ["Stefan Lendl"]
draft = false
+++

:ID:       230500d7-fbef-458d-9e60-f7bf5bc086ae

An indicator contains a specific mathematical function based on historical data
and tries to predict future price movements.

At certain points the indicator gives a [signal]({{< relref "Signal" >}}) which indicates to buy/sell at a
specific point of time and at a specific price level.

Each Indicator has various [input parameters]({{< relref "Input Parameters" >}}) which change the behavior of the
indicator. For example an input parameter of a moving average indicator will be
the period on which the moving average is calculated...

The aim of this project is to find the best suitable indicators with the best
signals and combine them to get even better results. Determining the quality of
an indicator is a complex problem. [Metrics]({{< relref "Metrics" >}}) describes this problem in more
detail.


## MetaTrader5 Indicators {#metatrader5-indicators}

In this project, indicators are used within MetaTrader5. In the MT5 community a
huge number of indicators is available with varying quality.
