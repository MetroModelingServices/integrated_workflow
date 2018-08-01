# MCE Supply Input Data Contract

**Emme modeller python script to calculate supply network reliability:** 
Run the following script in a Cygwin bash shell on the final assignment emmebank scenario's (pm2 and midday):
  ```
  python mce_reliability_prep.py
  ```
This script creates and populates link attributes needed to calculate @relvar. Cross-check these attributes with settings.yaml file so that all extra attributes have been populated on the network after running. The extra attribute @ctype is assummed to be copied from a prior scenario.

Next, run Emme to skim @relvar:
  ```
  auto_skims_MCE.mac
  ```
Resulting skims (pm2 and midday) will hold the travel time variance matrices. The square root of these matrices is used in the benefits calculator to arrive at the standard deviation (i.e. reliability) of travel time. 

**Emme modeller python script to export OMX matrices and extract link attribute data:**
Requires New_Project.emp files created at final assignment ./assign and new reliability ./skims directories. 

Run the following command in a Cygwin bash shell:

  ```
  bca_Emme_Export.bat
  ```
This script exports Emme network link attributes and needed OMX matrices (Emme derived). 

**ITHIM:**
Uses tdist, wdist, and PA walk/bike OMX matrices from demand model.

Run the following command in a Cygwin bash shell

  ```
  mce_ithim.R
  ```
To run the ITHIM R active transportation benefit calculator, configure the following settings at the top of the script:
  - projectDirectory_base = "data/base-data"
  - projectDirectory_build = "data/build-data"
  - projectDirectory_run = "data/run/ithimR"
  - GBDFileForITHIM = "burden.portland.csv"
  - PopulationFileForITHIM = "F.portland.csv"
  - WALK_SPEED = 3
  - BIKE_SPEED = 10
  - AVG_HH_SIZE = 2.4
  - DOLLARS_PER_DALY = 80000

The script will write out the dalys.csv output file with three columns - coc, dalys, and dollars.
