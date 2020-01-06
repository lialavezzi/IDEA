# IDEA
Geant4 simulation of the IDEA Detector

*******************************


 **TRACKER - Drift chamber + vertex detector** 
---
(DIRECTORY = DriftChamberPlusVertex)

-  Enter in simulation/ and edit envG4GMC.sh to change PRJBASE; then move in analyzer/ and edit envGMC.sh to change PRJBASE
   
-  To compile the simulation part:
   ```
   cd simulation
   source envG4GMC.sh
   cd g4GMC; make clean_all; make all	
   ```
   
-  To compile the analyzer:
   ```
   cd analyzer
   source envGMC.sh
   cd GMC
   source envMidasDAQ.sh
   make clean
   $ROMESYS/bin/romebuilder.exe -i GMC.xml
   make all
   ```
   
-  To compile readHits (which converts the hits.root file in a suitable format for GMCAnalyzer):
   ```
   cd ../simulation/g4GMC
   make readHits
   ```
   N.B. The previous compilation of the analyzer part is needed because of some dependencies required.
   
-  If everything works correctly, two executables are created in simulation/g4GMC/bin/Linux-g++: *g4GMC* and *readHits*     
   Now, before running the simulation, the IDEA geometry has to be initialized and exported in a gdml format. 
   Edit the geometry configuration file:
    ```
   simulation/g4GMC/geom_IDEA.txt	
   ```
   setting TRUE the boolean variable *writeGDML* and choosing the gdml file name.
   
   After that, to run the simulation step and generate events:
   ```
   ./bin/Linux-g++/g4GMC g4mac/runPFix-1.mac geom_IDEA.txt 1 pathTo/outputDIR
   ```
   where the arguments are: 1) Geant4 card to handle the simulation parameters, 2) geometry configuration, 3) number given to the simulation, 4) output directory
