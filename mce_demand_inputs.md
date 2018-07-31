# MCE Demand Input Data Contract

The following files specify the demand input data contract for the MCE tool. All input data are in OMX format and located in the ./\_mceInputs/ subdirectory for each alternative.
 
  - mce_input_cval.omx - Contains mf.cval (car ownership and workers by HIA) matrix. CVAL is defined as follows:
        
        mf.cval column order, by hia (listed as c <# cars> w <# workers>)
        - CVAL0 (mf.cval[,1:256]):     # of Household Cars = 0
          c0w0, c0w1, c0w2, c0w3,
        - CVAL1 (mf.cval[,257:448]):   # of Household Cars < # of Household Workers
          c1w2, c1w3, c2w3
        - CVAL2 (mf.cval[,449:640]):   # of Household Cars = # of Household Workers
          c1w1, c2w2, c3w3 
        - CVAL3 (mf.cval[,641:1024]):  # of Household Cars > # of Household Workers
          c1w0, c2w0, c2w1, c3w0, c3w1, c3w2
   
  - mce_input_parking_costs.omx - Contains vectors of long-term and short-term parking costs by TAZ
  
        ma.ltpkg: long-term parking costs by TAZ
        ma.stpkg: short-term parking costs by TAZ
   
  - mce_input_transit_fares.omx - Contains matrices of transit fares by income groups
  
        mf.trfare:      transit fares for all income groups (older model single-fare matrix, equivalent to new mf.trfare.mhi fares)
        mf.trfare.mhi:  transit fares for medium and high income groups
        mf.trfare.li:   transit fares for low income groups

  - mce_input_dest_choice_*trip purpose*.omx - Contains destination choice logsums vectors for each <trip purpose> (ho, hr, hs, hw, hc, nhnw, nhw, sch). Vectors are ordered by income group (where applicable)
  
        ma.<trip purpose>ldcls:  low income destination choice logsums
        ma.<trip purpose>mdcls:  medium income destination choice logsums
        ma.<trip purpose>hdcls:  high income destination choice logsums

  - mce_input_mode_choice_pa_*trip purpose*.omx - Contains mode choice production-to-attraction matrices for each <trip purpose> (ho, hr, hs, hw, hc, nhnw, nhw, sch). Where applicable by trip purpose, matrices are ordered by mode (da, dp, pa, tr, prtr, bike, walk), time of day (pk, op), cval, and income group (l, m, h)
  
        ma.<trip purpose>ldcls:  low income destination choice logsums
        ma.<trip purpose>mdcls:  medium income destination choice logsums
        ma.<trip purpose>hdcls:  high income destination choice logsums
