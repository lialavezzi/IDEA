# IDEA
Geant4 simulation of the IDEA Detector

*******************************


 **TRACKER - Drift chamber + vertex detector**
---

-  Enter in simulation/ and edit envG4GMC.sh to change PRJBASE
   ```
   cd simulation 
   ```
-  Enter in analyzer/ and edit envGMC.sh to change PRJBASE
   ```
   cd ../analyzer 
   ```
   
-  Then come back to simulation and load the environment variables:
   ```
   cd ../simulation
   source envG4GMC.sh
   ```

-  To compile the simulation part:
   ```
   cd g4GMC; make clean_all; make all	
   ```
