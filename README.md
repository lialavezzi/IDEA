# IDEA
Geant4 simulation of the IDEA Detector

*******************************


 **TRACKER - Drift chamber + vertex detector**
---

-  Enter in simulation/ and edit envG4GMC.sh to change PRJBASE
   ```
   cd simulation 
   ```

   Then load the environment variables:
   ```
   source envG4GMC.sh
   ```

-  To compile the simulation part:
   ```
   cd g4GMC; make clean_all; make all	
   ```