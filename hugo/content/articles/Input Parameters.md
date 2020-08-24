+++
title = "Input Parameters"
author = ["Stefan Lendl"]
draft = false
+++

usually referred to as **input**.


## Types of Input Parameters {#types-of-input-parameters}

An MT5 Indicator may have different types of inputs

-   Integer
-   Float
-   String
-   Boolean (Bool)
-   Enumerations (Enum)


### Continuous Input {#continuous-input}

An input is continuous if an adjacent input value only slightly changes
the function of an indicator.

Adjacent input values result in a continuous result space.

Typically **Integer** and **Float** inputs are continuous.

An example would be the the period of an moving average.


### Distinct (Non-Continuous) Input {#distinct-non-continuous-input}

If a distinct input value changes slightly, the function of the
indicator changes significantly. Adjacent input values result in
distinct results spaces.

Typically **Bool** and **Enum** inputs are distinct.


## Input Parameter ranges {#input-parameter-ranges}


### Ranged Inputs {#ranged-inputs}

An input parameter is **ranged** if a range of possible values is defined.
This is defined with `[default, start, stop, step]` values in indicator description.


### Concrete Inputs {#concrete-inputs}

An input is concrete if only a single, fixed value is possible.


### Ranged Indicator Set {#ranged-indicator-set}

-   An [indicator]({{< relref "Indicator" >}}) is considered ranged if **any** of the inputs is ranged.
-   An [indicator set]({{< relref "Indicator Set" >}}) is ranged if **any** of the indicators in the set is ranged.

When [adding a new indicator]({{< relref "Adding New Indicators" >}}) or a [sliced indicator set]({{< relref "Sliced Indicator Set" >}}) may have ranged inputs.

Continuous as well as distinct inputs may be ranged. In the case of distinct
inputs, the range is not logically coherent. This is sensible for defining a
wide range of inputs when adding a new indicator.


### Concrete Indicator Set {#concrete-indicator-set}

-   An [indicator]({{< relref "Indicator" >}}) is considered concrete if **all** of the inputs are concrete.
-   An [indicator set]({{< relref "Indicator Set" >}}) is concrete if **all** of the indicators in the set are concrete.

The result of the optimization procedure is always a concrete indicator set
which can be instantiated for forward testing and actual trading.
