# MCE Supply Input Data Contract

**Emme modeller python script to calculate supply network reliability:** 
Run the following script in a Cygwin bash shell on the final assignment emmebank scenario's (pm2 and midday):
  ```
  python mce_reliability_prep.py
  ```
This command creates link attributes needed to calculate @relvar. Cross-check with settings.yaml file that all extra attributes have been populated on the network after running python script. The extra attribute @ctype is assummed to be copied from a prior scenario.

Next, run Emme macro skim assignment:
  ```
  auto_skims_MCE.mac
  ```
Resulting skims will hold the travel time variance. The square root of these skims is used in the benefits calculator to arrive at the standard deviation (reliability) of travel time. 

**Emme modeller python script to export OMX matrices and extract link attribute data:**
(a) Requires New_Project.emp files created at reliability ./skims and final assignment ./assign directories. 

Run the following command in a Cygwin bash shell

  ```
  bca_Emme_Export.bat
  ```
This script exports Emme network link attributes and all OMX matrices (Emme derived). 

**ITHIM**
Requires tdist, wdist, and PA walk/bike OMX matrices from demand model. Runs via R script mce_ithim.R
