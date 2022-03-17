# Input files for the mozbc WRF-Chem preprocessor

Louis Marelle, 2022/03/17

Contains input files for the mozbc WRF-Chem utility. Mozbc is used to set the concentrations of chemical and aerosol species in wrfinput* and wrfbdy* files from global model input files. Mozbc is available at https://www.acom.ucar.edu/wrf-chem/download.shtml

File naming conventions:  
The 'mozbc_' prefix indicates that the file is for MOZART model input  
The 'cambc_' prefix indicates that the file is for CAM-Chem model input  
This prefix is followed by the name of the chemical mechanism for which this file should be used. Files for MOSAIC mechanisms (e.g. mozbc_saprc99_mosaic_8bin.inp) can be used for both the \_aq mechanism and base mechanism, and for both the \_vbs mechanism and the base mechanism
