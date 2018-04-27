# CMSSW_forZ4430
## How to setup CMSSW environment for Run-1 code:

1. `cmsrel CMSSW_5_3_22`
#### be aware that Git is not shipped automatically with such an old release

2. `cd CMSSW_5_3_22/src`

3. `git clone git@github.com:lecriste/CMSSW_forZ4430.git .`
#### the 'MuonAnalysis/MuonAssociators' and 'RecoVertex/PrimaryVertexProducer' packages have been pulled with
#### `git cms-cvs-history import V02-03-01 MuonAnalysis/MuonAssociators`
#### `git cms-cvs-history import V01-06-08 RecoVertex/PrimaryVertexProducer`
#### and in 'RecoVertex/PrimaryVertexProducer/src/DAClusterizerInZ_vect.cc' `#include "vdt/vdtMath.h"` has been replaced with `#include "DataFormats/Math/interface/VDTMath.h"`
#### Probably this is needed as well: https://hypernews.cern.ch/HyperNews/CMS/get/physTools/2746/1/1.html and to pull the 'RecoVertex/KinematicFit' package this is probably needed beforehand `git remote set-url official-cmssw git@github.com:cms-sw/cmssw.git`

#### Now you can add the analyzer
4. `git clone git@github.com:lecriste/Z4430.git UserCode`

5. `scram b`
