# Steps for running WRF-Chem preprocessors



## Get input meteorological data for initial/boundary conditions

TODO: Write README_metdata.md for detailed instructions on how to obtain meteorological data

Meteorological input data can be obtained fron CDS:  
ERA5 - https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-single-levels and https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-pressure-levels

Meteorological input data can also be obtained from ERA5:  
ERA5 reanalysis: https://rda.ucar.edu/datasets/ds633.0/  
FNL analysis: https://rda.ucar.edu/datasets/ds083.2/  
ERA-Interim: https://rda.ucar.edu/datasets/ds627.0/



## Setup and run the WRF preprocessor system (WPS)

TODO: Write README_wps.md for detailed instructions on how to compile and run WPS

The WPS code can be obtained from:  
https://github.com/wrf-model/WPS  
WPS also needs input data, available at:  
https://www2.mmm.ucar.edu/wrf/users/download/get_sources_wps_geog.html  
Download "Mandatory Fields". For WRF-Chem dust emissions, also download the field "erod".

### Set up WPS:  


TODO - This can be less detailed, this just needs to day where to take the example namelists and scripts and what they do. Also create a run archiving/reproducibility section at the top saying what files need to be kept after runs.

The WRF preprocessor (WPS) is run in 3 steps, using 3 executables: geogrid.exe, ungrib.exe, metgrid.exe. 

Create an empty case setup folder containing the WPS setup files, so that it is easy to reproduce and document the simulation. 
The setup folder should contain at least the following files:  
namelist.wps, jobscript_wps.sh, GEOGRID.TBL, Vtable, METGRID.TBL  
Example files for specific cases can be found in this repository. For new cases, copy the setup files from a similar case and modify the jobscript_wps.sh and namelist.wps  
TODO instructions on how to modify the namelist.

### Run WPS:  

TODO - This can be less detailed, this just needs to day where to take the example namelists and scripts and what they do. Also create a run archiving/reproducibility section at the top saying what files need to be kept after runs.

Create a temporary WPS run folder. Copy the input files from the WPS setup folder and the executables from the WPS source code to the WPS run folder. The run folder should contain the following files:  
geogrid.exe, link_grib.csh, ungrib.exe metgrid.exe, namelist.wps, jobscript_wps.sh, GEOGRID.TBL, Vtable, METGRID.TBL 

Launch jobscript_wps.sh in the cluster queue with qsub jobscript_wps.sh or sbatch jobscript_wps.sh. The jobscript runs the WPS executables in the following order:  
./geogrid.exe  
ln -s /path/to/metfiles/e5* . (for ERA5 data)  
./link_grib.csh e5 (for ERA5 data)     
./ungrib.exe  
./metgrid.exe  

Check that WPS ran properly:  
- geogrid.exe should produce geo* NetCDF files  
- ungrib.exe should produce FILE* files  
- metgrid.exe should produce met_em.dXX.yyyy-mm-dd_HH:MM:SS.nc NetCDF files  
If something went wrong errors can be investigated in .log files  

For polar runs, an extra preprocessor needs to be run right after WPS for setting up the sea ice and snow depth and albedo (update_seaice_depth_and_snow.m)  


## Run real.exe to create WRF-Chem input files

TODO: Write README_real.md for detailed instructions on how to run real.exe

Once the met_em.dXX.yyyy-mm-dd_HH:MM:SS.nc files are created by WPS, you need to run real.exe to create WRF-Chem input files (wrfinput_dXX, wfbdy_dXX, wrflowinp_dXX, wrffdda_dXX).

jobscript_real.exe


## Run the WRF-Chem preprocessors

TODO: Write README_chem_preprocessors.md for detailed instructions on how to compile and run the WRF-Chem preprocessors

### MEGAN bio emissions preprocessors (megan_bio_emiss preprocessor)

Rerun real.exe

### Get input chem data (CAM-Chem or MOZART)
Main download for NCAR/ACOM tools:
https://www2.acom.ucar.edu/wrf-chem/wrf-chem-tools-community

CAM-Chem output for initial and boundary conditions:
https://www2.acom.ucar.edu/gcm/cam-chem-output

### Chemical boundary conditions (mozbc preprocessor)

### Fire emissions (fire_emis preprocessor)

### Set up anthopogenic emissions

### Dry deposition and upper boundary conditions for photolysis (wesely and exo_coldens preprocessors)

