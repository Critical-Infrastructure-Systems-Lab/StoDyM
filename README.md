# StoDyM
For a given check dam system (dams' location and storage capacity) in the stream path of a catchment, StoDyM adopts an annual time step and calculates as output the annual changes in the dams' storage capacity (due to sediment trapping), the annual values of the Sediment Delivery Ratio (SDR, ratio between the sediment discharged at the catchment's outlet and delivered to the stream path), and the life expectancy of each check dam.

## Inputs:
* (c_pn, pa_v): First component is the pixel number (excluding "NoData" pixel) of the catchment's DEM raster and the second component is the area of a single pixel in km<sup>2</sup>.
* ste_tv: Threshold value of Sediment Trapping Efficiency (STE). It is given as 10% by threshold value.
* (dle_min, dle_max): First and second components of the dams' minimum and maximum life expectancy in years, respectively. 
* (csw_kg, s_sg): Fist component is the conversion of sediment mass unit to Kg and the second one is the sediment specific gravity in Kg/m<sup>3</sup>. For the present example, sediment mass is converted from Ton to Kg as 907.185, and the sediment specific gravity 2.65 is converted to 2650 Kg/m<sup>3</sup>
* sc_fn: File name of stream characteristics data (e.g., Shejiagou_Stream_Characteristics.xlsx), which contains the required information of each stream segment with the columns
  * SID: Identification number of the stream segment
  * NSID: Identification number of the next connected downstream segment 
  * DFA: Flow accumulation value at the potential dam location (extracted from the flow accumulation raster)
  * SSI: Sediment input to the stream segment (calculated by WaTEM/SEDEM)
* dtl_a: Array of dams' targeted location in terms of selected stream segments' identification number (please supply the value in ascending order and don't repeat any value since a segment cannot contain more than one dam)
* dsc_a: Array of dams' storage capacity according to the given order of dams' targeted location

## Output:
The output is an ordered dictionary with the keys:
* "Dam_Characteristics": Each row gives the dam's ID (DID), SID, initial storage capacity in m<sup>3</sup> (ISC), drainage area as a percentage of the total catchment area (IDA), and life expectancy in years (LE)
* "Storage_Variation": The normalized storage variation (i.e., the ratio between the available and initial storage capacity) of each dam with annual time step 
* "SDR_Variation": The variation of SDR with annual time step 
* "Summary": A short summary of check dam system's inital total storage capacity (ITSC), initial total drainage area (ITDA), average life expectancy in years (LE_A), and four objective values of multi-objective evoutionary algorithm in terms of average life expectancy (O-LE), storgae dynamics (O-SD), short-term SDR (O-SDR,ST), and long-term SDR (O-SDR,LT)

By default, the output of StoDyM cannot be saved in excel file. To save the data, please supply "excel_file=True" in the function "stodym_output_write(excel_file=False, stodym_fp="StoDyM_Output.xlsx")". The data will be saved in the current folder with default file name "StoDyM_Output.xlsx". If the data needs to be saved in other folder, please supply "stodym_fp="C\\Users\\My_Data.xlsx".   
