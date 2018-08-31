# MCE Demand Input Data Contract

The following files specify the demand input data contract for the MCE tool. All input data are in OMX or CSV format and located in the ./\_mceInputs/ subdirectory for each alternative.
 
 - mce_zone_vectors.csv - Contains a set of vectors for each zone. Vectors include the following:
         
        Parking costs assigned to each zone
         
            - ltpkg: long-term parking costs
            - stpkg: short-term parking costs
 
        Productions by zone for each <trip purpose> (ho, hr, hs, hw, hc, nhnw, nhw, sch).
        Vectors are ordered by income group (nhnw, nhw, and sch are not income specific):
  
            - <trip purpose>lpr:  low income productions
            - <trip purpose>mpr:  medium income productions
            - <trip purpose>hpr:  high income productions

        Destination choice logsums for each <trip purpose> (ho, hr, hs, hw, hc, nhnw, nhw, sch). 
        Vectors are ordered by income group (nhnw, nhw, and sch are not income specific):
  
            - <trip purpose>ldcls:  low income destination choice logsums
            - <trip purpose>mdcls:  medium income destination choice logsums
            - <trip purpose>hdcls:  high income destination choice logsums

  - mce_input_cval.csv - Contains car ownership and workers by HIA. File contains headers. CVAL is defined as follows:
        
        mf.cval column order, by hia (listed as c <# cars> w <# workers>)
        - CVAL0 (mf.cval[,1:256]):     # of Household Cars = 0
          c0w0, c0w1, c0w2, c0w3,
        
        - CVAL1 (mf.cval[,257:448]):   # of Household Cars < # of Household Workers
          c1w2, c1w3, c2w3
        
        - CVAL2 (mf.cval[,449:640]):   # of Household Cars = # of Household Workers
          c1w1, c2w2, c3w3 
        
        - CVAL3 (mf.cval[,641:1024]):  # of Household Cars > # of Household Workers
          c1w0, c2w0, c2w1, c3w0, c3w1, c3w2
   
  - mce_input_transit_fares.omx - Contains matrices of transit fares by income groups
  
        mf.trfare:      transit fares for all income groups (older model single-fare matrix, equivalent to new mf.trfare.mhi fares)
        mf.trfare.mhi:  transit fares for medium and high income groups
        mf.trfare.li:   transit fares for low income groups

  - mce_input_mode_choice_pa_*trip purpose*.omx - Contains mode choice production-to-attraction daily trip matrices for each <trip purpose> (ho, hr, hs, hw, hc, nhnw, nhw, sch). Where applicable by trip purpose, matrices are ordered by mode (da, dp, pa, tr, prtr, bike, walk), cval, income group (l, m, h), and time of day (pk, op). For trip purposes with all of these market segmentations (ho, hr, hs, hw, hc), the files included in each OMX are as follow (nhnw, nhw, and sch purposes have some derivation of these matrices, depending on the markets inherent in each trip purpose):
  
        mf.<trip purpose><mode>.<cval>.<income group>.<time of day>
        
        *trip purpose*
            - ho: home-based other
            - hr: home-based recreation
            - hs: home-based shop
            - hw: home-based work
            - hc: home-based college
            - nhnw: non-home non-work
            - nhw:  non-home work
            - sch:  K-12 school

          *mode*
            - da: drive alone (SOV)
            - dp: drive with passenger (HOV driver)
            - pa: passenger in HOV
            - tr: walk to transit
            - prtr: park-and-ride drive to transit trip (entire trip, production to/from attraction)
              - prtrl: portion of pnr trip in auto, production to/from pnr lot
              - prtrd: portion of pnr trip in transit, pnr lot to/from attraction  
            - bike
            - walk

          *cval*
            - cv0: zero car households
            - cv1: households in which cars < workers
            - cv23: households in which cars >= workers
            
          *income group*
            - l: low income
            - m: medium income
            - h: high income

          *time of day*
            - pk: peak period hours (6am-9am + 3pm-6pm)
            - op: off-peak hours (all other hours of day)

