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
1. Dataset of roads
TO SPECIFY

2. Geographic units data
- `Roman provinces`: The shapefile of Roman provinces in 200 CE (peak Roman Empire under the Severan dynasty) is based on 'roman-empire-ce-200-provinces.geojson' published by The Ancient World Mapping Centre and corrected by Adam Pazout in 2023. https://github.com/AWMC/geodata/tree/master/Cultural-Data/political_shading/roman_empire_ce_200_provinces

3. Dataset of ancient cities
- `Hanson J. W., An urban geography of the Roman world, 100 BC to AD 300. Oxford: Archaeopress; 2016. http://oxrep.classics.ox.ac.uk/oxrep/docs/Hanson2016/Hanson2016_Cities_OxREP.csv`
- `Hanson J. W, Ortman S. G., A systematic method for estimating the populations of Greek and Roman settlements. J Roman Archaeol. 2017;30: 301–324.`

## Scripts
### 1. network-analysis.Rmd
R script by Matteo Mazzamurro to analyse Roman roads as spatial networks.
