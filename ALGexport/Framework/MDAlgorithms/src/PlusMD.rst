.. algorithm:: PlusMD

.. summary:: PlusMD

.. aliases:: PlusMD

.. usage:: PlusMD

.. properties:: PlusMD

This algorithm sums two `MDHistoWorkspaces <MDHistoWorkspace>`__ or
merges two `MDEventWorkspaces <MDEventWorkspace>`__ together.

MDHistoWorkspaces
~~~~~~~~~~~~~~~~~

-  **MDHistoWorkspace + MDHistoWorkspace**

   -  The operation is performed element-by-element.

-  **MDHistoWorkspace + Scalar** or **Scalar + MDHistoWorkspace**

   -  The scalar is subtracted from every element of the
      MDHistoWorkspace. The squares of errors are summed.

MDEventWorkspaces
~~~~~~~~~~~~~~~~~

This algorithm operates similary to calling Plus on two
`EventWorkspaces <EventWorkspace>`__: it combines the events from the
two workspaces together to form one large workspace.

Note for file-backed workspaces
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The algorithm uses `CloneMDWorkspace <CloneMDWorkspace>`__ to create the
output workspace, except when adding in place (e.g. :math:`A = A + B` ).
See `CloneMDWorkspace <CloneMDWorkspace>`__ for details, but note that a
file-backed `MDEventWorkspace <MDEventWorkspace>`__ will have its file
copied.

-  If A is in memory and B is file-backed, the operation
   :math:`C = A + B` will clone the B file-backed workspace and add A to
   it.
-  However, the operation :math:`A = A + B` will clone the A workspace
   and add B into memory (which might be too big!)

Also, be aware that events added to a MDEventWorkspace are currently
added **in memory** and are not cached to file until `SaveMD <SaveMD>`__
or another algorithm requiring it is called. The workspace is marked as
'requiring file update'.

.. categories:: PlusMD