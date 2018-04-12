https://hackmd.io/Q0ecnGzqQvqOptvvfIgRJQ#Plotting-macros

# INSTALLATION
cmsrel CMSSW_9_4_1
cd CMSSW_9_4_1/src
cmsenv
export CMSSW_GIT_REFERENCE="/cvmfs/cms.cern.ch/cmssw.git.daily"
git cms-init
git remote add btv-cmssw https://github.com/cms-btv-pog/cmssw.git
git cms-addpkg DataFormats/BTauReco
git cms-addpkg PhysicsTools/PatAlgos
git cms-addpkg RecoBTag/Combined
git cms-addpkg RecoBTag/Configuration
git cms-merge-topic pablodecm:DeepFlavour\_9\_4\_1\_backport
git cms-merge-topic capalmer85:btagSFupdatesForTTbar
git clone https://github.com/cms-data/RecoBTag-Combined.git RecoBTag/Combined/data
git clone -b 9\_4\_X_v1.03 --depth 1 https://github.com/cms-btv-pog/RecoBTag-PerformanceMeasurements.git RecoBTag/PerformanceMeasurements
scram b -j8

