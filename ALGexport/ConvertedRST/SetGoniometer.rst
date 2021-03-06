.. algorithm:: SetGoniometer

.. summary:: SetGoniometer

.. aliases:: SetGoniometer

.. usage:: SetGoniometer

.. properties:: SetGoniometer

Use this algorithm to define your goniometer. Enter each axis in the
order of rotation, starting with the one closest to the sample.

You may enter up to 6 axes, for which you must define (separated by
commas):

-  The name of the axis, which MUST match the name in your sample logs.
   You can specify a number, and a log value will be created
   (GoniometerAxis?\_FixedValue, where ? is the axis number)
-  The X, Y, Z components of the vector of the axis of rotation.
   Right-handed coordinates with +Z=beam direction; +Y=Vertically up
   (against gravity); +X to the left.
-  The sense of rotation as 1 or -1: 1 for counter-clockwise, -1 for
   clockwise rotation.

The run's sample logs will be used in order to determine the actual
angles of rotation: for example, if you have an axis called 'phi', then
the first value of the log called 'phi' will be used as the rotation
angle. Units are assumed to be degrees.

.. categories:: SetGoniometer