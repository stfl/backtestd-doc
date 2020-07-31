usually only called an **input**

  

An MT5 Indicator may have different types of inputs

  

*   Integer
*   Float
*   String
*   Boolean
*   Enumerations (Enum)

  

Continuous Input
----------------

An input is continuous if an adjacent input value only slightly changes the function of an indicator.

Adjacent input values result in a continuous result space.

  

Typically Integer and Float inputs are continuous.

An example would be the the period of an moving average.

Distinct (Non-Continuous) Input
-------------------------------

If a distinct input value changes slightly, the function of the indicator changes significantly. Adjacent input values result in distinct results spaces.

  

Typically bool and enum inputs are distinct.