Here are some examples of usage of StartLiveData, most use the
FakeEventDataListener so they will always work, but this can be swapped
for any instrument such as OFFSPEC, GEM, HYSPEC etc.

Note: After running each of these you will need to cancel the ongoing
data loading by cancelling the MonitorLiveData algorithm. You will find
this by clicking the details button in the bottom left corner of
Mantidplot.

Just Live Event Data
^^^^^^^^^^^^^^^^^^^^

.. code:: python

    StartLiveData(UpdateEvery='1.0',Instrument='FakeEventDataListener',
      OutputWorkspace='live')

Live Event Rebin using an algorithm and plotting
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code:: python

    StartLiveData(UpdateEvery='1.0',Instrument='FakeEventDataListener',
      ProcessingAlgorithm='Rebin',ProcessingProperties='Params=10e3,1000,60e3;PreserveEvents=1',
      OutputWorkspace='live')
    plotSpectrum('live', [0,1])

Live Event Rebin using a python script
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The script can be as simple or complicated as you want, you have to call
the input workspace input, and the output workspace at the end output.

.. code:: python

    script='Rebin(InputWorkspace=input,OutputWorkspace=output,Params="40000,100,50000")'
    StartLiveData(UpdateEvery='1.0',Instrument='FakeEventDataListener',  
      ProcessingScript=script,ProcessingProperties='Params=10e3,1000,60e3;PreserveEvents=1',  
      OutputWorkspace='live')
    plotSpectrum('live', [0,1])

Live Event Pre and post processing
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This uses rebin to select a region of time of flight, and then after the
data is accumulated it uses SumSpectra to sum all of the data into a
single spectrum. When using post processing you have to give the
accumulation workspace a name.

.. code:: python

    StartLiveData(UpdateEvery='1.0',Instrument='FakeEventDataListener',  
      ProcessingAlgorithm='Rebin',ProcessingProperties='Params=10e3,1000,60e3;PreserveEvents=1',  
      OutputWorkspace='live', AccumulationWorkspace="accumulation",
      PostProcessingAlgorithm="SumSpectra",PostProcessingProperties="")
    plotSpectrum('live', 0)

Live Histogram Data and plotting
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

For Histogram data the accumulationMethod needs to be set to Replace,
you will get a warning otherwise.

.. code:: python

    StartLiveData(UpdateEvery='1.0',Instrument='OFFSPEC',
     AccumulationMethod="Replace", OutputWorkspace='live')
    plotSpectrum('live', [0,1])

