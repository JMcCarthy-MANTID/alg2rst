.. algorithm:: LoadLiveData

.. summary:: LoadLiveData

.. aliases:: LoadLiveData

.. usage:: LoadLiveData

.. properties:: LoadLiveData

This algorithm is called on a regular interval by the
`MonitorLiveData <MonitorLiveData>`__ algorithm. **It should not be
necessary to call LoadLiveData directly.**

.. figure:: images\LoadLiveData_flow.png
   :alt: LoadLiveData_flow.png

   LoadLiveData\_flow.png
Data Processing
~~~~~~~~~~~~~~~

-  Each time LoadLiveData is called, a chunk of data is loaded from the
   `LiveListener <LiveListener>`__.

   -  This consists of all the data collected since the previous call.
   -  The data is saved in a temporary `workspace <workspace>`__.

-  You have two options on how to process this workspace:

Processing with an Algorithm
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

-  Specify the name of the algorithm in the *ProcessingAlgorithm*
   property.

   -  This could be, e.g. a `Python Algorithm <Python Algorithm>`__
      written for this purpose.
   -  The algorithm *must* have at least 2 properties: *InputWorkspace*
      and *OutputWorkspace*.
   -  Any other properties are set from the string in
      *ProcessingProperties*.
   -  The algorithm is then run, and its OutputWorkspace is saved.

Processing with a Python Script
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

-  Specify a python script in the *ProcessingScript* property.

   -  This can have several lines.
   -  Two variables have special meaning:

      -  *input* is the input workspace.
      -  *output* is the name of the processed, output workspace.

   -  Otherwise, your script can contain any legal python code including
      calls to other Mantid algorithms.
   -  If you create temporary workspaces, you should delete them in the
      script.

Data Accumulation
~~~~~~~~~~~~~~~~~

-  The *AccumulationMethod* property specifies what to do with each
   chunk.

   -  If you select 'Add', the chunks of processed data will be added
      using `Plus <Plus>`__ or `PlusMD <PlusMD>`__.
   -  If you select 'Replace', then the output workspace will always be
      equal to the latest processed chunk.
   -  If you select 'Append', then the spectra from each chunk will be
      appended to the output workspace.

.. raw:: html

   <div style="border:1px solid #5599FF; {{Round corners}}; margin: 15px;">

A Warning About Events
^^^^^^^^^^^^^^^^^^^^^^

Beware! If you select *PreserveEvents* and your processing keeps the
data as `EventWorkspaces <EventWorkspace>`__, you may end up creating
**very large** EventWorkspaces in long runs. Most plots require
re-sorting the events, which is an operation that gets much slower as
the list gets bigger (Order of N\*log(N)). This could cause Mantid to
run very slowly or to crash due to lack of memory.

.. raw:: html

   </div>

Post-Processing Step
~~~~~~~~~~~~~~~~~~~~

-  Optionally, you can specify some processing to perform *after*
   accumulation.

   -  You then need to specify the *AccumulationWorkspace* property.

-  Using either the *PostProcessingAlgorithm* or the
   *PostProcessingScript* (same way as above), the
   *AccumulationWorkspace* is processed into the *OutputWorkspace*

.. categories:: LoadLiveData