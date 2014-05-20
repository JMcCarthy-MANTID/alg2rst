.. algorithm:: LoadIsawUB

.. summary:: LoadIsawUB

.. aliases:: LoadIsawUB

.. usage:: LoadIsawUB

.. properties:: LoadIsawUB

Saves the UB matrix in a workspace to an ISAW-style UB matrix ASCII
file.

You can use the `SaveIsawUB <SaveIsawUB>`__ algorithm to save to this
format.

The matrix saved is the transpose of the UB Matrix. The UB matrix maps
the column vector (h,k,l ) to the column vector (q'x,q'y,q'z).
\|Q'\|=1/dspacing and its coordinates are a right-hand coordinate system
where x is the beam direction and z is vertically upward. (IPNS
convention)

.. categories:: LoadIsawUB