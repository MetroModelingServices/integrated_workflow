# MCE Supply Input Data Contract -- 24 hour assignments

The following files specify the supply input data contract for the MCE tool. These inputs are specific to the 24 hour peak-spread assignments. All input data are OMX or CSV format and located in the ./\_mceInputs/ subdirectory for each alternative.
 
 For each input, <time period> defines the hour of the assignment period. Format is <start + end hour>. Time periods are as follow:
   0001 = 00:00 - 01:00 (midnight - 1am)
   0102 = 01:00 - 02:00 (1am - 2am)
   0203 = 02:00 - 03:00 (2am - 3am)
   0304 = 03:00 - 04:00 (3am - 4am)
   0405 = 04:00 - 05:00 (4am - 5am)
   0506 = 05:00 - 06:00 (5am - 6am)
   0607 = 06:00 - 07:00 (6am - 7am)
   0708 = 07:00 - 08:00 (7am - 8am)
   0809 = 08:00 - 09:00 (8am - 9am)
   0910 = 09:00 - 10:00 (9am - 10am)
   1011 = 10:00 - 11:00 (10am - 11am)
   1112 = 11:00 - 12:00 (11am - 12pm)
   1213 = 12:00 - 13:00 (12pm - 1pm)
   1314 = 13:00 - 14:00 (1pm - 2pm)
   1415 = 14:00 - 15:00 (2pm - 3pm)
   1516 = 15:00 - 16:00 (3pm - 4pm)
   1617 = 16:00 - 17:00 (4pm - 5pm)
   1718 = 17:00 - 18:00 (5pm - 6pm)
   1819 = 18:00 - 19:00 (6pm - 7pm)
   1920 = 19:00 - 20:00 (7pm - 8pm)
   2021 = 20:00 - 21:00 (8pm - 9pm)
   2122 = 21:00 - 22:00 (9pm - 10pm)
   2223 = 22:00 - 23:00 (10pm - 11pm)
   2324 = 23:00 - midnight (11pm - midnight)
 
 
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
        
        mf.am2rls:  AM2 SOV O-D reliability skims
        mf.md1rls:  MD1 SOV O-D reliability skims
        
 - mce_input_links_PM2.csv / mce_input_links_MD1.csv - Contains a list of all links in the PM2 or MD1 networks and their attributes. Attributes are defined as follows:

        i:                   from-node ID
        j:                   to-node ID
        @amrmp:              AM hourly ramp meter rate
        @barrier:            indicates presence of barrier (1)
        @cap:                hourly capacity
        @centerturn:         indicates presence of center turn lane (1)
        @divhwy:             indicates if link represents a divided highway (1)
        @dwdist:             downstream interchange distance (for calculating @relvar)
        @fwcap:              capacity of freeway link
        @htkad:              additional travel time used by heavy trucks in assignment
        @htvol:              assigned volume of heavy trucks (passenger car equivalents)
        @hvol:               assigned volume of High Occupancy Vehicles (2+ persons)
        @lanes2:             lanes = 2
        @lanes3:             lane = 3
        @lanes4:             lanes = 4
        @losc:               LOS C+
        @loscart:            LOS C+ arterial
        @losd:               LOS D+
        @lose:               LOS E+
        @losfh:              LOS F high +
        @losfl:              LOS F low +
        @losflart:           LOS F low + arterial
        @mb:                 mid-block capacity of link
        @mdrmp:              midday hourly ramp meter rate
        @mpa:                link is located within Metropolitan Planning Area boundary (1)
        @mtkad:              additional travel time used by heavy trucks in assignment
        @mtvol:              assigned volume of heavy trucks (passenger car equivalents)
        @noisef:             noise benfefit
        @pmrmp:              PM hourly ramp meter rate
        @relvar:             reliability travel time variance
        @signal:             indicates presence of signal control at j-node (1)
        @spd35:              speed 35
        @spd40:              speed 40
        @spd45:              speed 45
        @spd50:              speed 50
        @spd50p:             speed 50+
        @spd70:              speed 70
        @speed:              free flow travel speed 
        @stop:               indicates presence of signal control at j-node (1)
        @svol:               assigned volume of Single Occupancy Vehicles 
        @thrwy:              indicates whether link is part of RTP-defined regional *throughway* network (1)
        @tknet:              indicates whether link is part of RTP-defined regional *freight* network (1) 
        @tkpth:              additional *weight* for truck travel times used in assignments 
        @trkad:              additional travel time used by all trucks in assignment 
        @ttoll:              additional travel time equivalent for trucks of *toll* on link  
        @ul3:                approach capacity (capacity at intersection)
        @updist:             upstream interchange distance (for calculating @relvar)
        @urbrur:             urban vs. rural geography used for safety benefit (uses @mpa as definition)
        @waterf:             water quality benefit
        @zone:               transporation analysis zone associated with link
        additional_volume:   not used
        auto_time:           assigned travel time
        auto_volume:         assigned volume (passenger car equivalents)
        aux_transit_volume:  not used
        data1:               user defined data field 1 (ul1)
        data2:               user defined data field 2 (ul2)
        data3:               user defined data field 3 (ul3)
        length:              length in miles
        num_lanes:           number of lanes
        type:                facility type:  1 = transit-only, 2/3 = pedestrian-only 10 = freeways, 19 = HOV lane, 20 = highway,
                                            30 = arterials and collectors, 70 = freeway off-ramp, 79 = freeway on-ramp,
                                            999 = centroid connectors
        volume_delay_func:   volume delay function
 
  

