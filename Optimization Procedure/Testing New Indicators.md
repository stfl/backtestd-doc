# Testing New Indicators
After a new indicator is defined in the system it shall be tested. Testing means calculating the fitness function (metric) for each input parameter set.

The current implementation plan is to process all possible input parameters. This has $O(n^m)$.
$n$ possible values per input. $m$ different free inputs.

If an indicator has 10k input parameter and it is combined with another indicator of also 10k inputs the resulting search space is 10k^2 = 100M

This shows that size of the search space also increases by $O(m^p)$ which overall results in $O(n^{m \cdot p})$ where $p$ is the number of indicators in the combined indicator set.

The result will be a table with maybe 100k rows. One row for each possible input combination with the resulting metrics.

In order to reduce the search space it is necessary to [[Reducing the result set]]