# Mesoscale Ocean Eddies along the U.S. West Coast.

The ocean, like the atmosphere, is a fundamentally turbulent system. When we observe 
animations of the ocean’s sea level evolution, what is most striking is that all of the world’s 
oceans are full of mesoscale (30-1000 km) eddies and meanders and at all latitude bands. 

Recently, Escudier et al. (2016) tested three different eddy detection and tracking methods
for the outputs of a high‐resolution simulation in the Western Mediterranean Sea in order to 
extract mesoscale eddy characteristics, and the results are compared with the same eddy 
statistics derived from satellite altimetry maps over the same period. One particularly interesting
observation is that there may be a correlation between radius and duration of the eddies,
and long‐lived eddies tend to grow more rapidly toward bigger size. 

The goal of this project is to test this assumed correlation on a different data set over the 
Eastern Pacific. The shoreline region along Oregon and California is studied in wide
contexts, nevertheless a newly compiled flow field data set by Risien and Strub (2016) is not
yet explored in all details.

Escudier et al., J. Geophys. Res. Oceans, 121, 3990–4006 (2016).
https://agupubs.onlinelibrary.wiley.com/doi/epdf/10.1002/2015JC011371 

Tasks

## Data aquisition  

A recent effort by Risien and Strub (2016) extends the work of Saraceno et al. (2008) by 
improving the temporal resolution from weekly to daily sea level anomaly fields, over a longer period, 
and by expanding the region to include the entire U.S. West Coast. The result is a geostrophic flow 
field resolving mesoscale eddies in details. 

C.M. Risien, and P.T. Strub, Scientific Data, Vol. 3, Article number: 160013 (2016). 
https://doi.org/10.1038/sdata.2016.13

NetCDF data  (22 individual NetCDF files have been added to a single TAR file) can be 
downloaded from this link (registration is not required):
https://ir.library.oregonstate.edu/concern/datasets/fn107383f?locale=en

Extra Python modules: netCDF4, Basemap 

## Eddy detection and tracking

Please carefully read  Section 3 (Eddy detection methods) in Escudier et al. (2016) ,
and the related papers on the methodologies (new publications do not repeat all technical details).
Method I. is based on detecting closed contours of sea level anomalies by means of
the altimetry records. Methods II. and III. require geostrophic velocities, which are computed
already (2D vector components) and directly available in the downloaded data set. Note that according 
to Escudier et al. (2016), the three methods give different results for the shapes and locations 
of the detected eddies, and no method appears to stand out as superior to the others.

Bonus task (worth of a scientific paper): Try to understand and explain where the different
methods leak, even propose improvements.

## Comparative eddy statistics

Please calculate the size distribution functions shown in Figure 7 in Escudier et al. (2016),
furthermore the correlation plot in Fig. 8. Critically compare the three methods, and the
overall results with that of Escudier et al. (2016) for the Western Mediterranean Sea.
