**Python**

``   LoadIsawDetCal("SNAP_4111","SNAP.DetCal")``

**C++**

| ``   IAlgorithm* alg = FrameworkManager::Instance().createAlgorithm("LoadIsawDetCal");``
| ``   alg->setPropertyValue("InputWorkspace", "SNAP_4111");``
| ``   alg->setPropertyValue("Filename", "SNAP.DetCal");``
| ``   alg->execute();``
