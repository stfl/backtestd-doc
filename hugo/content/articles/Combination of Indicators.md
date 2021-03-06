+++
title = "Combination of Indicators"
author = ["Stefan Lendl"]
draft = false
+++

:CUSTOM_ID: combining
:ID:       5db8c230-8ac7-4564-a544-fd0d4372523c

The resulting metric for combined indicators **must** be larger than the
metric for each individual indicator or indicator sub-sets.

This ensures that adding a single indicator to the set actually is
beneficial.


## Implications {#implications}


### Indicators may not be compatible {#indicators-may-not-be-compatible}

:PROPERTIES: :CUSTOM_ID: indicators-may-not-be-compatible :END:
Good individual results may be bad in combination with other indicators.


### Bad individual results may lead to good results when combined {#bad-individual-results-may-lead-to-good-results-when-combined}

Bad individual results must not be fully eliminated but when selecting a
candidate for combining with other indicators a weighted selection
process should be applied.l


### The actual quality of an algorithm can only be determined if all functions are filled with indicators. {#the-actual-quality-of-an-algorithm-can-only-be-determined-if-all-functions-are-filled-with-indicators-dot}

If all functions are filled profit may be a valid [metric]({{< relref "Metrics" >}}).
