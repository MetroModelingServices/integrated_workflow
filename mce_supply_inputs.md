# MCE Supply Input Data Contract

**Emme modeller python script to calculate supply network reliability:** (a) run mce_reliability_prep.py on final assignment networks to create link attributes needed to calculate @relvar (b) skim @relvar via auto_skims_MCE.mac with existing volume-delay functions. The extra attribute @ctype is assummed to be copied from a prior scenario. Cross-check with settings.yaml file that all extra attributes have been populated on the network after running python script. This skim will hold the travel time variance. The square root of the skim is used in the benefits calculator to arrive at the standard deviation (reliability) of travel time.

(a) run bca_Emme_Export.py script to export Emme network link attributes and all OMX matrices (Emme-derived).  
