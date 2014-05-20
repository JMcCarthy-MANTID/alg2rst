.. algorithm:: ConvertSpectrumAxis2

.. summary:: ConvertSpectrumAxis2

.. aliases:: ConvertSpectrumAxis2

.. usage:: ConvertSpectrumAxis2

.. properties:: ConvertSpectrumAxis2

Converts the representation of the vertical axis (the one up the side of
a matrix in MantidPlot) of a Workspace2D from its default of holding the
spectrum number to the target unit given - theta, elastic Q and elastic
Q^2.

The spectra will be reordered in increasing order by the new unit and
duplicates will not be aggregated. Any spectrum for which a detector is
not found (i.e. if the instrument definition is incomplete) will not
appear in the output workspace.

.. categories:: ConvertSpectrumAxis2