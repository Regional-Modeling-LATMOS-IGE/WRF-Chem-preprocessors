# Steps for running WRF-Chem pre processors


## Step 1. Follow WRF dynamics setup

### Get input meteorological data for initial/boundary conditions

TODO: Write README_metdata.md for detailed instructions on how to obtain meteorological data

Data can be obtained fron CDS:  
ERA5 - https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-single-levels and https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-pressure-levels

Data can also be obtained from ERA5:  
ERA5 reanalysis: https://rda.ucar.edu/datasets/ds633.0/  
FNL analysis: https://rda.ucar.edu/datasets/ds083.2/  
ERA-Interim: https://rda.ucar.edu/datasets/ds627.0/

### Run the WRF preprocessor (WPS)

TODO: Write README_wps.md for detailed instructions on how to compile and run WPS

The WPS code can be obtained from:  
https://github.com/wrf-model/WPS  
WPS also needs input data, available at:  
https://www2.mmm.ucar.edu/wrf/users/download/get_sources_wps_geog.html  
Download Mandatory Fields. For WRF-Chem, also download the field "erod".

Set up WPS:  

Run WPS:  

Check that WPS ran properly:  
Several met_em.dXX.yyyy-mm-dd_HH:MM:SS.nc files should be created.  

For polar runs, an extra preprocessor needs to be run right after WPS for setting up the sea ice and snow depth and albedo (update_seaice_depth_and_snow.m)

### Create WRF input files (real.exe)


## Step 2. Set up WRF-Chem preprocessors

### MEGAN bio emissions preprocessors (megan_bio_emiss preprocessor)

Rerun real.exe

### Get input chem data (CAM-Chem or MOZART)

### Chemical boundary conditions (mozbc preprocessor)

### Fire emissions (fire_emis preprocessor)

### Set up anthopogenic emissions

### Dry deposition and upper boundary conditions for photolysis (wesely and exo_coldens preprocessors)

