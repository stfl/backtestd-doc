+++
title = "Reducing the result set"
author = ["Stefan Lendl"]
draft = false
+++

## Reducing n {#reducing-n}

_n_ is the number of values of a single input parameter. /The lengths of
the input sets are obviously not all the same but for O() notation this
does not matter./

The size of _n_ is defined by the number of possible values. The range,
describing this has a start, a stop and a step value.

-   If we reduce the move start and stop closer together.
-   In case of a continuous input parameter the step value can be
    increased.


## Reducing m {#reducing-m}

The number of free (variable) inputs can be reduces by setting inputs to
a fixed value.

Reducing the length of an input range to 1.


## Reducing p {#reducing-p}

The number of input indicators in a indicator set has a significant
impact of the search space.

Ideally each indicator is tested individually.


## Reduction Procedure {#reduction-procedure}

-   Testing a single indicator with an appropriate size of the search
    space.
-   Reducing the indicators _n_ and _m_ by analyzing the results.
    Segmenting (Slicing) the search space of the indicator.
-   Using the segmented indicator input space to combine with another
    indicator
-   Segment and reduce the search space of the combination (indicator set)
    by analyzing the result space.
-   Combine the indicator set with yet another indicator
-   ... continue until all functions of the algorithm are filled

This procedure is a tree search. depth-first or breadth-first search is
possible.

This ensures that _n_ and _m_ are continuously reduced and non-relevant
input parameters are not considered in the following rounds.

Each tested indicator or indicator set may have multiple configurations
that can be used for combinations.

For example an indicator with a single input may have good results at a
range of `[3, 8]` as well as `[14, 19]`. Both ranges may be used to
combine with another indicator.

-   continue with a genetic algorithm to breed between the leafs of the
    search tree
