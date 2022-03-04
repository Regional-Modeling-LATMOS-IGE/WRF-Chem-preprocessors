# Steps for running WRF-Chem pre processors


## Step 1. Follow WRF dynamics setup
### Get input met data
ERA5, FNL, ERA-Interim
### WPS
Extra preprocessor for polar runs (sea ice and snow depth and albedo)
### REAL

## Step 2. Set up WRF-Chem preprocessors
### MEGAN bio emissions preprocessors (megan_bio_emiss preprocessor)
Rerun real
### Get input chem data (CAM-Chem or MOZART)
### Chemical boundary conditions (mozbc preprocessor)
### Fire emissions (fire_emis preprocessor)
### Set up anthopogenic emissions
### Dry deposition and upper boundary conditions for photolysis (wesely and exo_coldens preprocessors)

