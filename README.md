# Investigating the 2021 Houston Winter Storm Blackouts
*EDS 223: Geospatial Analysis & Remote Sensing*
*UCSB Masters of Environmental Data Science*

## Purpose

This repository contains the workflow, data, and outputs for Homework 3 of EDS 223, 
completed by Melannie Moreno Rolón. The project analyzes the February 2021 winter 
storms in Houston, Texas, which caused widespread power outages. Using NASA VIIRS 
night-light data, OpenStreetMap building and road data, and U.S. Census 
socioeconomic data, the analysis estimates the spatial extent of blackouts, 
identifies affected residential areas, and examines the socioeconomic context of 
power loss. The workflow was conducted entirely in R and documented in a Quarto 
report integrating geospatial data analysis, raster operations, and vector-based 
overlay techniques.

## Description of Repository

This repository contains spatial and statistical analyses exploring the impact 
of the February 2021 winter storms on power distribution and socioeconomic 
inequality in Houston, Texas. By comparing satellite imagery before and after 
the storms, the study identifies blackout areas, filters out non-residential 
and highway-adjacent regions, and estimates the number of homes likely affected.
Census and income data are then used to evaluate whether blackout exposure varied 
across different income levels. The results are presented as a series of maps 
and a boxplot visualizing median household income distributions for tracts that 
did and did not experience blackouts.

## Repository Structure

```
C:.
│   .gitignore
│   LICENSE
│   README.html
│   README.md
│   texas-winterstorm-2021.Rproj
│   texas_winterstorm_2021.qmd
│
└───data
    │   gis_osm_buildings_a_free_1.gpkg
    │
    ├───ACS_2019_5YR_TRACT_48_TEXAS.gdb
    │   └───ACS_2019_5YR_TRACT_48_TEXAS.gdb
    │       └───census tract gdb files
    │
    ├───gis_osm_roads_free_1.gpkg
    │
    └───VNP46A1
        └───VIIRS data files

```
## Data Access

- **NASA VIIRS Nighttime Lights (VNP46A1)**: Daily radiance data downloaded from 
NASA’s Black Marble product suite. These data were used to measure changes in 
light intensity before and after the blackout (February 7 and February 16, 2021).

- **OpenStreetMap Roads and Buildings**: Extracted from the OpenStreetMap (OSM) 
Geofabrik Texas dataset. Roads were filtered for fclass = 'motorway' to represent 
major highways, while buildings were filtered for residential types 
(e.g., house, apartments, detached).

- **U.S. Census ACS 2019 (5-Year Estimates)**: Geodatabase sourced from the U.S. 
Census Bureau containing tract-level demographic and income information for the 
state of Texas. Median household income (variable B19013e1) was used to analyze 
socioeconomic differences in blackout exposure.

To reproduce the analysis, ensure that the following R packages are installed:
`sf`, `terra`, `tmap`, `tidyverse`, `here`, and `ggspatial`.

## Acknowledgements

This project was made possible through the use of open-source spatial data and 
R-based geospatial analysis tools.

- NASA Black Marble VIIRS data were obtained from the NASA Earth Observations platform.

- OpenStreetMap data were accessed via Geofabrik’s open data repository.

- ACS 2019 Census Data were downloaded from the U.S. Census Bureau and accessed through the TIGER/Line shapefiles and geodatabase products.

Special thanks to the developers of the R packages used in this analysis, including 
{sf}, {terra}, {tmap}, {ggspatial}, and {tidyverse}, which enabled geospatial data 
processing, raster manipulation, and visualization in Quarto.

This work was completed as part of EDS 223: Geospatial Analysis & Remote Sensing 
at the University of California, Santa Barbara, under the guidance of course instructor 
Annie Adams and TA Alessandra Vidal Meza, whose feedback and teaching 
supported the completion of this project.

## Citations

NASA Earth Science Division. (2021). Black Marble VIIRS Nighttime Lights (VNP46A1). Retrieved November 10, 2025, from https://blackmarble.gsfc.nasa.gov/

OpenStreetMap contributors. (n.d.). Texas OSM Roads and Buildings Data (Geofabrik). Retrieved November 10, 2025, from https://download.geofabrik.de/north-america/us/texas.html

U.S. Census Bureau. (2019). American Community Survey (ACS) 5-Year Estimates, 2019. Retrieved November 10, 2025, from https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-data.html

## Author

Melannie Moreno Rolón

## License

This repository is distributed under the MIT License
