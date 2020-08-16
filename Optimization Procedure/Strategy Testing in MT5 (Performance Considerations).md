Optimization Strategies in MT5
=============================

Complete Optimization
---------------------

Runs with all combination of the defined input parameters (ranges)

Genetic Algorithm
-----------------

Uses a genetic algorithm to find the best input parameter combination.

This strategy results in approx 10000 parameters tested.

_According to the MT5 documentation \[TODO\] this procedure can be configured but I haven't found this in MT5..._

Initialization Overhead
=======================

When starting the Strategy tester from outside the program it has a significant initialization overhead where MT5 downloads the history data and initializes the local and remote agents.

If the test run has very few input parameter combinations the init overhead is significantly longer than the actual calculation of the parameters.

Empirically, the threshold is around 10000 where the test actually takes longer than the initialization. This of course depends on the hardware.

Multi-Currency Backtesting
==========================

The trading strategy in this project aims to use the same configuration on all Forex currency pairs. Therefore, a given input parameter needs to be evaluated on all relevant symbols (currency pairs).

The genetic algo described above more or less randomly chooses input parameters so running the genetic algo individually on all symbols does not results in an appropriate overlap.

  

A modification of the backtesting expert allows to run on all symbols simultaneously.

The performance of this approach is significantly lower due to additional initialization overhead. I assume this is caused by having to initialize the history for all 28 symbols over and over again.

  

Although, this modification allows using MT5's genetic algo optimization strategy on all symbols.

  

It turns out, when running the complete optimization strategy it is faster to run it individually on all symbols and merging the results in post-processing. This has the benefit of having individual results.

The is a threshold where the multi-currency expert is actually faster due to differences in initialization. This threshold was seen to be at around 5000-10000 in my current setup.

Performance Conclusion
======================

Due to the massive overhead caused by test initialization it is essential for the overall performance to aim for a test size of larger than 10000. Smaller test sets will not increase the performance.

  

Very large test sets will also result in an significant execution time. (TODO)

This execution time can be reduced by adding more processing power through adding remote agents for strategy testing, which is a built-in feature of MT5.