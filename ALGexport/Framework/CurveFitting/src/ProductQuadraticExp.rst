.. algorithm:: ProductQuadraticExp

.. summary:: ProductQuadraticExp

.. aliases:: ProductQuadraticExp

.. usage:: ProductQuadraticExp

.. properties:: ProductQuadraticExp

This fit function computes the product of a linear and exponential
function. See `ExpDecay <ExpDecay>`__ and QuadraticBackground for
details on the component functions.

:math:`(\mbox{A0}+\mbox{A1}\times x+\mbox{A2}\times x^2) \times  \mbox{Height}\times \exp(-\frac{x}{\mbox{Lifetime}})`

This function may be used with the `Fit <Fit>`__ algorithm. However, it
was originally added to Mantid as a named function for the purposes of
detector efficiency calibration. Also see
`ProductLinearExp <ProductLinearExp>`__.

.. categories:: ProductQuadraticExp