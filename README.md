# CMSSW_forZ4430
# How to setup CMSSW environment for Run-1 code:

cmsrel CMSSW_5_3_22
# be aware that Git is not shipped automatically with such an old release

cd cmsrel CMSSW_5_3_22/src

git clone git@github.com:lecriste/CMSSW_forZ4430.git .
# the MuonAnalysis/MuonAssociators and RecoVertex/PrimaryVertexProducer packages have been pulled with
# git cms-cvs-history import V02-03-01 MuonAnalysis/MuonAssociators
# git cms-cvs-history import V01-06-08 RecoVertex/PrimaryVertexProducer
# and in RecoVertex/PrimaryVertexProducer/src/DAClusterizerInZ_vect.cc '#include "vdt/vdtMath.h"' has been replaced with '#include "DataFormats/Math/interface/VDTMath.h"'

# Now you can add the analyzer
git clone git@github.com:lecriste/Z4430.git UserCode
