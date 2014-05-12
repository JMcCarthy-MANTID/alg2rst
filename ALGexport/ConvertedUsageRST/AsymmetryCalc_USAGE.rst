**Python**

``   OutWS = AsymmetryCalc("EmuData","1.0","0,1,2,3,4","16,17,18,19,20")``

**C++**

| ``   IAlgorithm* alg = FrameworkManager::Instance().createAlgorithm("AsymmetryCalc");``
| ``   alg->setPropertyValue("InputWorkspace", "EmuData");``
| ``   alg->setPropertyValue("OutputWorkspace", "OutWS");``
| ``   alg->setPropertyValue("Alpha", "1.0");``
| ``   alg->setPropertyValue("ForwardSpectra", "0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15");``
| ``   alg->setPropertyValue("BackwardSpectra", "16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31");``
| ``   alg->execute();``
| ``   Workspace* ws = FrameworkManager::Instance().getWorkspace("OutWS");``
