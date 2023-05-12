This directory should contain zip files downloaded from various municipal or state websites containing GIS or other tabular data.

## Data that I used:

* SanGIS shapefiles are available for free at https://rdw.sandag.org/
  * I didn't include these in the repository because I didn't want to risk copyright infringement, but you can easily
    create an account and download the data for free.  I did, however, include the PDF documentation for the shapefile
    layers.
  * The "Parcels" shapefile layer was used to get all the parcels geometries, as well as assessor value, taxable status,
    Tax Rate Area (TRA) field, landuse, zoning, and many more useful fields.
  * The "Municipal_Boundaries" shapefile layer was used to help select and filter parcels, as well as draw municipal
    boundaries.
  * The "LANDUSE_CURRENT" shapefile layer was used to draw recognizable features as a map "baselayer" which can be
    helpful for geographic context.

* tralist.pdf is a random PDF I found from <https://www.sandiegocounty.gov/content/dam/sdc/auditor/trb2021/tralist.pdf>
  which contains all of the 2021 Tax Rate Area (TRA) info which joins to the "TRANUM" field in the Parcels shapefile.
  This is necessary to calculate the actual property tax for each parcel, because there's no one simple tax rate that
  applies everywhere.

* `../shoreline/pacific_ocean_SD.shp`
  * This is a custom polygon representing the pacific ocean just off the southern california coast which I adapted from
    Shoreline Mapping Program CA1101A data, found at: https://www.ngs.noaa.gov/NSDE/

## Data that I did NOT use:

* San Diego Tax Roll data files, $86. see https://www.sandiegocounty.gov/content/sdc/auditor/trdf.html
  * I used to be under the impression that I needed this data based on this [forum post from the Strong Town San Diego
    forum](https://forum.strongtownsandiego.org/viewtopic.php?f=2&t=628), but in the end I decided to rely on my own
    estimates of the tax revenue based on combining TRA data with parcel assessment values.
