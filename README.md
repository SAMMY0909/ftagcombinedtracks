Authors: Alexander Khanov & Soumyananda Goswami
with inputs from FTAG package maintainers, the CERN ATLAS Codebase, GitLab ATLAS Software Tutorials (https://atlassoftwaredocs.web.cern.ch/ABtutorial/), xAOD mini Derivation Tutorials (https://twiki.cern.ch/twiki/bin/viewauth/AtlasComputing/XAODMiniTutorialDerivations) and members of the Flavour Algorithms group

To setup the package, carry out these commands in succession.
Only works for Release 22 stuff.
```
setupATLAS --quiet
lsetup git
git clone https://:@gitlab.cern.ch:8443/atlas-flavor-tagging-tools/FlavourTagPerformanceFramework.git
cd FlavourTagPerformanceFramework
git checkout freshstart_r22
git atlas init-workdir  https://:@gitlab.cern.ch:8443/anburger/athena.git
mv btagAnalysis athena/
cd athena
git checkout release/22.6.3
#git atlas addpkg DerivationFrameworkExamples
git atlas addpkg BTagging
git atlas addpkg JetTagTools
cd ..
git clone https://:@gitlab.cern.ch:8443/sgoswami/ftag_combinedtracks.git
cd ftag_combinedtracks
\cp -r each_login.sh ../
\cp -r README.md ../
\cp -r setuppatch ../
\cp -r combinedpatch ../

cd ..
rm -rf ftag_combinedtracks
\cp -r setuppatch/athena .
\cp -r setuppatch/scripts .
\cp -r combinedpatch/athena . 
rm -rf setuppatch
rm -rf combinedpatch 
source scripts/setup.sh
```
