# StoDyM
For a given check dam system (dams' location and storage capacity) in the stream path of a catchment, StoDyM adopts an annual time step and calculates as output the annual changes in the dams' storage capacity (due to sediment trapping), the annual values of the Sediment Delivery Ratio (ratio between the sediment discharged at the catchment's outlet and delivered to the stream path), and the life expectancy of each check dam.

## Input
* (c_pn, pa_v): First component is th pixel number (excluding "NoData" pixel) of the catchment's DEM raster (c_pn) and the second component is the area of a single pixel in km<sup>2</sup>.
* ste_tv: Threshold value of Sediment Trapping Efficiency (STE). If it is 10%, please supply it as 0.1
* (dle_min, dle_max): First and second components are the dams' minimum and maximum life expectancy, respectively. 
* (csw_kg, s_sg): Fist component is the conversion of sediment mass unit to Kg and the second one is the sediment specific gravity in Kg/m<sup>3</sup>. For the present example, sediment mass is converted from ton to Kg as 907.185, and the sediment specific gravity 2.65 is converted to 2650 Kg/m<sup>3</sup>
* sc_fn: File name of stream characteristics data (e.g., Shejiagou_Stream_Characteristics.xlsx), which contains the required information of each stream segemnt with the columns
  * SID: Identification number of the stream segment
  * NSID: Identification number of the next connected downstream segment 
  * DFA:
  * SSI:

## Output
* 1
* 2
* 3
* 4
