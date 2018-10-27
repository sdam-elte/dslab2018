# Lightning Hotspots on Earth

The main subject of this project is to recalculate the results of Albrecht et al. (2016), who
analyzed 16 years of the Lightning Imaging Sensor (LIS) data using the Tropical Rainfall 
Measuring Mission (TRMM) satellite observations. The mission finished in 2015, however
the International Space Station (ISS) is equipped with an identical sensor, and new
data are available since March of 2017 (regularly updated).

Lightning hotspots are geographic locations of extraordinary high frequencies of flashes,
such as Lake Maracaibo in Venezuela or the Congo basin in Africa. The required statistical
analysis of flash frequencies is more than a simple reproduction, because the geographic
distributions might change as a result of global climate change, therefore a regular
reanalysis is a highly relevant task.

Link to the key paper: https://journals.ametsoc.org/doi/10.1175/BAMS-D-14-00193.1

Tasks

## Data aquisition

These ISS LIS data are considered provisional files indicating that the algorithm is still
under development and the data may contain errors. Dataset available online from the 
NASA EOSDIS Global Hydrology Resource Center:
You need to create and use an Earthdata Login to download or order GHRC data.
The starting link to the data sets:
https://ghrc.nsstc.nasa.gov/lightning/data/data_lis_iss.html
 
Note that the collection contains two separate sets, the so called "Provisional Science
Data" and the "Provisional Backgrounds". The first set is for all information about the
detected lightnings (time, location, luminosity, etc..), the second is for the background
images taken by the CCD sensor. At the moment, only the "Non-Quality Controlled"
versions are available on full length.

## Data conversion

Data and some software are available in in opening page. Two formats are downloadable:
hdf , precisely HDF-4 (https://en.wikipedia.org/wiki/Hierarchical_Data_Format)
nc , precisely NetCDF-4 (https://en.wikipedia.org/wiki/NetCDF)
Python tools are available mostly for HDF-5 records, therefore a (batch) conversion might
be necessary by external utilities. Nevertheless the module netCDF4 can be used
directly, the price is somewhat larger disk space demand for the data.

## Understanding data structure

The elementary signal is an ‘event’, a single pixel that exceeds the background threshold in a 
single recording frame of 2 ms. A ‘group’ is defined as neighboring ‘events’ that occur in the same
2 ms time frame. ‘Flash’ is defined as a cluster of ‘groups’ within 330 ms and 5.5 km of each
other, probably this category is the closest to the everyday observations what we call “lightning
stroke”, where ‘groups’ form the branches. Highest in the hierarchy, the product ‘area’ as a cluster
of ‘flashes’ helps to study multicellular thunderstorms.
Link with all the useful links:
https://ghrc.nsstc.nasa.gov/pub/lis/iss/doc/isslis_dataset.pdf

## Analyzing lightning hotspots and statistics

Besides calculating frequency distributions, the recommended Python tool for mapping and
visualization is the "Basemap" module. Please recalculate Table 1 and replot Figure 2
of Albrecht et al. (2016), and critically compare the ISS results with the earlier observations.
