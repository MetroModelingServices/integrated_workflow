# MCE Supply Input Data Contract

**Emme modeller python script to calculate supply network reliability:**
(a) run mce_reliability_prep.py on final assignment network to prepare network attributes needed to calculate @relvar
(b) skim @relvar via auto_skims_MCE.mac with existing volume-delay functions. This skim will hold the travel time variance. The square root of the skim is used in the benefits calculator to arrive at the standard deviation (reliability) of travel time.

**Emme modeller python script to export OMX matrices and format link data:**
