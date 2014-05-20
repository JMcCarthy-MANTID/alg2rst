.. algorithm:: FindSXPeaks

.. summary:: FindSXPeaks

.. aliases:: FindSXPeaks

.. usage:: FindSXPeaks

.. properties:: FindSXPeaks

Detector-space, single crystal peak finding. Finds peaks by searching
through each spectra and looking for high intensity bins. If a bin has
high intensity it is a candidate for a peak.

Notable points:

-  The highest intensity bin is taken to be the peak, so only finds one
   peak per spectra
-  Peaks that are not above the background are culled. The background is
   calculated as the average of the start and end intensity multiplied
   by the provided SignalBackground parameter.
-  Calculated Qlab follows the Busy, Levy 1967 convention.

.. categories:: FindSXPeaks