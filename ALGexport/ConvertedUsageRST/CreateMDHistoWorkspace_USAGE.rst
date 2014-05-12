The following example creates a 2D MDHistoWorkspace called *demo* with 3
bins in each dimension and and extents spanning from -1 to 1 in each
dimension. The first dimension is called A, and has units of U, the
second is called B and has units of T.

``CreateMDHistoWorkspace(SignalInput='1,2,3,4,5,6,7,8,9',ErrorInput='1,1,1,1,1,1,1,1,1',Dimensionality='2',Extents='-1,1,-1,1',NumberOfBins='3,3',Names='A,B',Units='U,T',OutputWorkspace='demo')``

The following example creates a 1D sine function

| `` import math``
| `` ``
| `` signals=[]``
| `` errors=[]``
| `` pi = 3.14159``
| `` extents = [-2*pi,2*pi]``
| `` nbins = [100]``
| `` dimensionality = 1``
| `` step = float((extents[1] - extents[0])/nbins[0])``
| `` for i in range(0, nbins[0]):``
| ``     x = i*step;``
| ``     signals.append(math.sin(x))``
| ``     errors.append(math.cos(x))``
| ``CreateMDHistoWorkspace(SignalInput=signals,ErrorInput=errors,Dimensionality=dimensionality,Extents=extents,NumberOfBins=nbins,Names='x',Units='dimensionless',OutputWorkspace='demo')``
