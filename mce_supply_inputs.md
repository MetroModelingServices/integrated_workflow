# MCE Supply Input Data Contract

The following files specify the supply input data contract for the MCE tool. All input data are OMX or CSV format and located in the ./\_mceInputs/ subdirectory for each alternative.
 
 - mce_input_skims.omx - Contains all skim matrices for the alternative. A list of the matrices follows:
  
        mf.pm2Hpe:  PM2 heavy truck O-D trips (PCEs)
        mf.pm2Mpe:  PM2 medium truck O-D trips (PCEs)
        mf.md1Hpe:  MD1 heavy truck O-D trips (PCEs)
        mf.md1Mpe:  MD1 medium truck O-D trips (PCEs)
        
        mf.tdist:   shortest path auto distance between zones
        mf.wdist:   shortest path walk distance between zones
        
        mf.am2stt:  AM2 SOV O-D travel times
        mf.am2htt:  AM2 HOV O-D travel times
        mf.md1stt:  MD1 SOV O-D travel times
        mf.md1htt:  MD1 HOV O-D travel times
        
        -all transit times are *perceived* (weighted)
        mf.amwt1:   AM2 initial transit wait time
        mf.amwt2:   AM2 additional transit wait time
        mf.amwalk:  AM2 total tranist walk time
        mf.amxfr:   AM2 total transfers (does not include initial boarding)
        mf.amtbiv:  AM2 bus in-vehicle time
        mf.amtliv:  AM2 lrt (MAX) in-vehicle time
        mf.amtriv:  AM2 heavy rail (WES) in-vehicle time
        mf.amtsciv: AM2 streetcar in-vehicle time 
        mf.amtbriv: AM2 brt in-vehicle time
        
        mf.amivt:   AM2 total in-vehicle time (bus + lrt + heavy rail + streetcar + brt)
        
        mf.mdwt1:   MD1 initial transit wait time
        mf.mdwt2:   MD1 additional transit wait time
        mf.mdwalk:  MD1 total tranist walk time
        mf.mdxfr:   MD1 total transfers (does not include initial boarding)
        mf.mdtbiv:  MD1 bus in-vehicle time
        mf.mdtliv:  MD1 lrt (MAX) in-vehicle time
        mf.mdtriv:  MD1 heavy rail (WES) in-vehicle time
        mf.mdtsciv: MD1 streetcar in-vehicle time
        mf.mdtbriv: MD1 brt in-vehicle time
        
        mf.mdivt:   MD1 total in-vehicle time (bus + lrt + heavy rail + streetcar + brt)
        
        mf.pkdptr:  total peak period transit trips in O-D format. trips are adjusted to flow in PM peak direction. 6am-9am + 3pm-6pm
        mf.opdptr:  total off-peak period transit trips in O-D format. trips are not adjusted. all other times of day
        
        mf.am2rls:  AM2 SOV O-D reliability skims
        mf.md1rls:  MD1 SOV O-D reliability skims
        
 - mce_input_links_PM2.csv - Contains a list of all links in the PM2 network and their attributes.
 - mce_input_links_MD1.csv - Contains a list of all links in the MD1 network and their attributes.
 
  
