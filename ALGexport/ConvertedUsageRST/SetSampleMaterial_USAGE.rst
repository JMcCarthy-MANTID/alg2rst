Setting the sample by simple formula
''''''''''''''''''''''''''''''''''''

SetSampleMaterial(InputWorkspace='IRS26173',ChemicalFormula='Fe')

Setting the sample by a more complex formula
''''''''''''''''''''''''''''''''''''''''''''

SetSampleMaterial(InputWorkspace='IRS26173',ChemicalFormula='Al2-O3',
UnitCellVolume='253.54', ZParameter='6')

Setting the sample by specific values
'''''''''''''''''''''''''''''''''''''

SetSampleMaterial(InputWorkspace='IRS26173',AtomicNumber=26,AttenuationXSection=2.56,ScatteringXSection=11.62,SampleNumberDensity=0.0849106)

Extracting the set values out by python
'''''''''''''''''''''''''''''''''''''''

sam = ws.sample() mat = sam.getMaterial() print mat.absorbXSection()
1.3374 print mat.cohScatterXSection() 339.1712 print mat.name() C2 H4
print mat.totalScatterXSection() 339.1712
