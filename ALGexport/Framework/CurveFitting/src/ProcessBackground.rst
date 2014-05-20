.. algorithm:: ProcessBackground

.. summary:: ProcessBackground

.. aliases:: ProcessBackground

.. usage:: ProcessBackground

.. properties:: ProcessBackground

The algorithm ProcessBackground() provides several functions for user to
process background to prepare Le Bail Fit.

Simple Remove Peaks
^^^^^^^^^^^^^^^^^^^

This algorithm is designed for refining the background based on the
assumption that the all peaks have been fitted reasonably well. Then by
removing the peaks by function 'X0 +/- n\*FWHM', the rest data points
are background in a very high probability.

An arbitrary background function can be fitted against this background
by standard optimizer.

Automatic Background Points Selection
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This feature is designed to select many background points with user's
simple input. User is required to select only a few background points in
the middle of two adjacent peaks. Algorithm will fit these few points
(*BackgroundPoints*) to a background function of specified type.

.. categories:: ProcessBackground