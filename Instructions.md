# Steps for running WRF-Chem pre processors


## Step 1. Follow WRF dynamics setup

### Get input meteorological data for initial/boundary conditions

See README_metdata.md for detailed instructions on how to obtain meteorological data

Data can be obtained fron CDS:
ERA5 - https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-single-levels and https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-pressure-levels

Data can also be obtained from ERA5:
ERA5 reanalysis: https://rda.ucar.edu/datasets/ds633.0/ or 
FNL analysis: https://rda.ucar.edu/datasets/ds083.2/
ERA-Interim: https://rda.ucar.edu/datasets/ds627.0/

### Run the WRF preprocessor (WPS)

Extra preprocessor for polar runs (sea ice and snow depth and albedo)

### Create WRF input files (real.exe)


## Step 2. Set up WRF-Chem preprocessors

### MEGAN bio emissions preprocessors (megan_bio_emiss preprocessor)

Rerun real.exe

### Get input chem data (CAM-Chem or MOZART)

### Chemical boundary conditions (mozbc preprocessor)

### Fire emissions (fire_emis preprocessor)

### Set up anthopogenic emissions

### Dry deposition and upper boundary conditions for photolysis (wesely and exo_coldens preprocessors)

