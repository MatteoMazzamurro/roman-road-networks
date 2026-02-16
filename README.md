# Roman Road Networks

## About
*This project analyses Itiner-e, a high-resolution dataset of roads of the Roman Empire, using network theory*

## Authors

* Matteo Mazzamurro [![](https://orcid.org/sites/default/files/images/orcid_16x16.png)](https://orcid.org/0009-0004-4454-1551), PSNP, Aarhus University
* Tom Brughmans [![](https://orcid.org/sites/default/files/images/orcid_16x16.png)](https://orcid.org/0000-0002-1589-7768), PSNP, Aarhus University
* Adam Pažout, Pau de Soto, María Coto-Sarmiento, Clara Filet, Eduardo Herrera Malatesta, Magnus Nielsen, Gustav Emil Ølgaard, Peter Vahlstrup

## License
CC-BY-SA 4.0, see attached [License.md](./License.md)
(Updated from GNU General Public License v3.0 via commit 24a9f3b)

## Data
1. Data sets of roads
- `Roman roads`: export from itiner-e provided by the authors:
de Soto, P. et al. (2025) A High-Resolution Dataset of Roads of the Roman Empire: Itiner-e static version 2024. Zenodo. https://doi.org/10.5281/zenodo.17122148
- `modern roads`: v10 of the ESRI world road network, which can be downloaded from https://www.arcgis.com/home/item.html?id=83535020ce154bd5a498957c159e3a99

2. Geographic units data
- `Roman provinces`: The shapefile of Roman provinces in 200 CE (peak Roman Empire under the Severan dynasty) is based on 'roman-empire-ce-200-provinces.geojson' published by The Ancient World Mapping Centre and corrected by Adam Pazout in 2023. https://github.com/AWMC/geodata/tree/master/Cultural-Data/political_shading/roman_empire_ce_200_provinces
- `modern world countries`: boundaries can be downloaded from https://hub.huwise.com/explore/assets/world-administrative-boundaries/export/

3. Dataset of ancient cities
- `Hanson J. W., An urban geography of the Roman world, 100 BC to AD 300. Oxford: Archaeopress; 2016. http://oxrep.classics.ox.ac.uk/oxrep/docs/Hanson2016/Hanson2016_Cities_OxREP.csv`
- `Hanson J. W, Ortman S. G., A systematic method for estimating the populations of Greek and Roman settlements. J Roman Archaeol. 2017;30: 301–324.`
- Provincical capitals assembled by Tom Brughmans

4. Ancient sites from Pleiades available from https://pleiades.stoa.org/downloads

## Systems requirements
This document uses R version 4.3.0 (2023-04-21 ucrt). 
It relies on the following versions of the packages:
* tidyverse     2.0.0
* dplyr         1.1.4
* sf            1.0.13
* spatstat      3.0.7
* raster        3.6.26
* units         0.8.2
* igraph        1.4.3
* sfnetworks    0.6.3
* spatgraphs    3.4
* ggraph        2.1.0
* ggspatial     1.1.9
* RColorBrewer  1.1.3
* colorRamps    2.3.1
* cowplot       1.1.3
* deldir        1.0.9
* cccd          1.6
* Desctool      0.99.58
* stplanr       1.2.3

## Installation guide
Install R. (Following the instructions at https://www.r-project.org/)

*tidyverse* and *dplyr* offer a collection of methods for data analysis, that we use for data cleaning and visualisation. We use *sf* to read and handle shapefiles, *spatstat* for point processes and observation windows, *raster* to manage the coordinate projections, and *units* to ensure correct handling of distance units. We use *igraph* and *sfnetworks* to construct our network objects. *ggraph* allows to visualise graph objects based on the ggplot2 framework (ggplot2 is included in tidyverse), and *ggspatial* adds other visual features for maps. *RColorBrewer* and *colorRamps* allow efficient management of colours, and *cowplot* is used to create separate images of legends. *deldir*, *spatgraphs*, and *cccd* are used to create spatial graph models. *DescTools* is used to compute the Gini coefficient of inequality. *stplanr* is used to add a buffer zone around a sf.

One needs to install them if they are not installed yet.
```{r install packages}
packages_to_install <- required_packages[!(required_packages %in% installed.packages()[,"Package"])]
if(length(packages_to_install)) install.packages(packages_to_install)
```

Finally, one needs to load them
```{r load packages}
invisible(lapply(required_packages, library, character.only = TRUE))
```

If a package has been updated since the release of this code, using the newer version may cause issues.
If this is the case, one can try to solve them by installing the specific versions of the packages by uncommenting and running the following code. 
Note, however, that these older versions of the packages may not be available for newer versions of R, in which case it will be necessary to switch to an older version of R to run the code (please refer to the cran.r website on how to do that: https://cran.r-project.org/index.html).
```{r install specific package versions}
\#install devtools if not already installed
if (!"devtools" %in% installed.packages()[,"Package"]) install.packages("devtools")

\#load devtools
library(devtools)

\#install specific versions of the packages
install_version("tidyverse", version = "2.0.0")
install_version("dplyr", version = "1.1.4")
install_version("sf", version = "1.0.13")
install_version("spatstat", version = "3.0.7")
install_version("raster", version = "3.6.26")
install_version("units", version = "0.8.2")
install_version("igraph", version = "1.4.3")
install_version("sfnetworks", version = "0.6.3")
install_version("spatgraphs", version = "3.4")
install_version("ggraph", version = "2.1.0")
install_version("ggspatial", version = "1.1.9")
install_version("RColorBrewer", version = "1.1.3")
install_version("colorRamps", version = "2.3.1")
install_version("cowplot", version = "1.1.3")
install_version("deldir", version = "1.0.9")
install_version("cccd", version = "1.6")
install_version("Desctool", version = "0.99.58")
install_version("stplanr", version = "1.2.3")
 
\#load packages
invisible(lapply(required_packages_analysis, library, character.only = TRUE))
```

Full installation runtime of 4min49secs on
Laptop:  Dell Pro 14 Plus
Processor: Intel(R) Core(TM) Ultra 7 155H, 3800 Mhz, 16 Cores, 22 Logical Processors 
RAM: 16 GB 
OS: Microsoft Windows 11 Enterprise


## Demo TO DO
Run network-analysis-demo.Rmd in R. Ensure data is accessible in folder ("./data").

## Instruction for use
Run network-analysis.Rmd in R. Ensure data is accessible in folder ("./data").


