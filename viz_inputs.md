# Visualizer Input Data Contract

The following files specify the input data contract for the visualizer:

  - BENEFITS_FILE - a CSV file with each row a benefit measure and columns for Processor, Target, Description, each COC, Everybody.  See `aggregate_results.csv`.
  
| Processor              | Target                     | Description                    | coc_ext_lowengpro | coc_ext_age18or65 | everybody    |
|------------------------|----------------------------|--------------------------------|-------------------|-------------------|--------------|
| aggregate_demographics | hhs_for_the_coc            | total hhs for each coc         | 41539       | 631411      | 1189040  |
| aggregate_zone         | travel_options_benefit     | travel options benefit         | 21712843       | 369077215       | 674153738  |
| aggregate_zone         | veh_ownership_cost_benefit | vehicle ownership cost benefit | 6089       | -274529      | -276373 |
| aggregate_od           | physical_activity_benefit  | physical activity benefit      | -717    | -12533     | -23838 |

  - ZONE_BENEFITS_FILE - a CSV file of zone-based benefit measures.  Each row is a zone, and zones are in order.  See `aggregate_zone_benefits.csv`.
 
 | access_benefit_hbc | access_benefit_hbo | access_benefit_hbr | access_benefit_hbs | access_benefit_hbw | access_benefit_nhbnw | access_benefit_nhbw | access_benefit_sch | travel_options_benefit |
|--------------------|--------------------|--------------------|--------------------|--------------------|----------------------|---------------------|--------------------|------------------------|
| 0                  | 0                  | 0                  | 0                  | 0                  | 0                    | 0                   | 0                  | 0                      |
| -9.777402105       | 640.8279788        | 675.2277384        | 379.3699471        | 336.2980021        | 131452.1726          | 111.5441305         | 3.953275123        | 133589.6163            |
| 2.634822825        | 976.3548076        | 934.0187585        | 694.4114082        | 373.8674394        | -112663.2608         | 189.6223647         | 22.12307884        | -109470.2281           |
| -0.426769676       | 1073.827903        | 910.1136113        | 654.2042721        | 781.1778018        | 127664.4209          | 166.3176037         | -12.02121191       | 131237.6141            |
| -28.22580526       | 2124.205518        | 1786.018884        | 1175.625051        | 1679.898238        | 511470.8777          | 334.2504754         | -31.6707784        | 518510.9793            |
  
  - COUNTIES_COC_FILE - a CSV file with each zone as a row (in order) and a column for membership in each COC + a county name column.  See `cocs.csv`
  
| lowengpro_zone | age18or65_zone | County    |
|----------------|----------------|-----------|
| 0              | 0              | Multnomah |
| 0              | 0              | Multnomah |
| 0              | 0              | Multnomah |
  
