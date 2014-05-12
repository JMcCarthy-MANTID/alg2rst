**Python**

``   CreateDummyCalFile("SNAP_4111","output.cal")``

**C++**

| ``   IAlgorithm* alg = FrameworkManager::Instance().createAlgorithm("CreateCalFileByNames");``
| ``   alg->setPropertyValue("InputWorkspace", "SNAP_4111");``
| ``   alg->setPropertyValue("CalFilename", "output.cal");``
| ``   alg->execute();``
