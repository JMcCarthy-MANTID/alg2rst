.. algorithm:: OptimizeCrystalPlacement

.. summary:: OptimizeCrystalPlacement

.. aliases:: OptimizeCrystalPlacement

.. usage:: OptimizeCrystalPlacement

.. properties:: OptimizeCrystalPlacement

This algorithm basically optimizes h,k, and l offsets from an integer by
varying the parameters sample positions, sample orientations ( chi,phi,
and omega), and/or the tilt of the goniometer for an experiment.

-If the crystal orientation matrix, UB, was created from one run, that
run may not need to have its goniometer settings optimized. There is a
property to list the run numbers to NOT have their goniometer settings
changed. This entry is IGNORED if the tilt or sample positions are
included in the optimization. In this case NONE of the goniometer
angles, relative to any tilt, will be changed.

-The goniometer angles displayed are relative to the tilt,i,e, phi is
the rotation around the axis perpendicular to the tilted plane. The
resultant PeaksWorkspace has the goniometer angles relative to the Y and
Z axes at that time.

-The crystal orientation matrix, UB, from the PeaksWorkspace should
index all the runs "very well". Otherwise iterations that slowly build a
UB with corrected sample orientations may be needed.

-The parameters for the tilt are GonRotx, GonRoty, and GonRotz in
degrees. The usage for this information is as follows:

``    rotate('x',GonRotx)*rotate('y',GonRoty)*rotate('z',GonRotz)* SampleOrientation( i.e. omegaRot*chiRot*phiRot)).``

| ``-Note: To optimize by the tilt in the goniometer and then by the angles or by the sample position, it is possible to``
| ``run with one optimization, then using the resultant PeaksWorkspace for input, run another optimization.``

| ``Rerunning the same optimization with the result is also a good idea. If the first guess is very close, the optimize algorithm``
| ``does try cases far away and may not get back to the best value.  Check the chisquared values.  If they increase, that optimization``
| ``should probably not be used.``

.. categories:: OptimizeCrystalPlacement