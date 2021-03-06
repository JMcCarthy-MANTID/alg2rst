.. algorithm:: ComputeSensitivity

.. summary:: ComputeSensitivity

.. aliases:: ComputeSensitivity

.. usage:: ComputeSensitivity

.. properties:: ComputeSensitivity

Calculate the EQSANS detector sensitivity. This workflow algorithm uses
the reduction parameters found in the property manager object passed as
the ReductionProperties parameter to load the given data file, apply all
the necessary corrections to it and compute the sensitivity correction.

Setting the PatchWorkspace property allows you to patch areas of the
detector. All masked pixels in the patch workspace will be patched. The
value assigned to a patched pixel is the average of all unmasked pixels
in this patched pixel's tube.

.. categories:: ComputeSensitivity