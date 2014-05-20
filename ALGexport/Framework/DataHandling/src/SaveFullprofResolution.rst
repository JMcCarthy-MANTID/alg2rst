.. algorithm:: SaveFullprofResolution

.. summary:: SaveFullprofResolution

.. aliases:: SaveFullprofResolution

.. usage:: SaveFullprofResolution

.. properties:: SaveFullprofResolution

Fullprof's resolution file contains the peak profile parameters and some
powder diffractometer's geometry related parameters in a certain format.
This algorithm reads a TableWorkspace containing all the information
required by Fullprof's resolution file, and write out a text file
conforming to that resolution file's format.

Peak Profile Supported
----------------------

Here is the list of peak profile supported by this algorithm:

-  Thermal Neutron Back-to-back Exponential Convoluted with Pseudo-voigt
   peak profile.

Instrument Profile Parameter TableWorkspace
-------------------------------------------

TableWorkspace as the input of this algorithm can be generated from
*CreateLeBailFitInput*, *RefinePowderInstrumentParameters* or
*LeBailFit*. To be noticed that the TableWorkspace output from
*RefinePowderInstrumentParameters* is usually an intermediate product.

Input TableWorkspace must have two columns, "Name" and "Value", as
column 0 and 1. There is no restriction on other columns.

How to use algorithm with other algorithms
------------------------------------------

This algorithm is designed to work with other algorithms to do Le Bail
fit. The introduction can be found in `Le Bail Fit <Le Bail Fit>`__.

.. categories:: SaveFullprofResolution