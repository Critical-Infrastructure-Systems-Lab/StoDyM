# StoDyM
For a given check dam system (dams' location and storage capacity) in the stream path of a catchment, StoDyM adopts an annual time step and calculates as output the annual changes in the dams' storage capacity (due to sediment trapping), the annual values of the Sediment Delivery Ratio (ratio between the sediment discharged at the catchment's outlet and delivered to the stream path), and the life expectancy of each check dam.

## Input

### catchment pixel
* Tuple of pixel number of catchment's DEM and the pixel area in km^2. For the present example 
c_pn, pa_v = (12419, 20**2/10**6)
* ste_tv = 0.1  # dam Sediment Trapping Efficiency (STE) threshold value
ca_km2 = c_pn * pa_v  # catchment area (km^2)
dle_min, dle_max = (20, 30)  # dam life expectancy minimum and maxiumum values
csw_kg, s_sg = (907.185, 2650)  # connversion of sediment unit to Kg and sediment specific graity 

## Output
