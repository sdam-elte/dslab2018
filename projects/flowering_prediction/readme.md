# Predicting flowering dates based on meteorological information
### Consultant: Imre Jánosi

Many plants under mid-latitude climate have evolved to time flowering to maximize 
outcrossing, minimize exposure to damaging frosts, and synchronize development with 
soil moisture and nutrient availability. Understanding the environmental cues that influence 
the timing of reproductive budburst will be important for predicting how flowering phenology 
of plants will change with a changing climate. 
Recent [paper](https://www.sciencedirect.com/science/article/pii/S0378112717314834).

In the framework of this project, flowering dates of 329 perennial species over the period 
of 1968-2000 are evaluated by means of time series of daily environmental parameters 
spanning several months backward from the flowering event. Such problem is vastly over-complete 
for traditional methods: the number of explanatory variables overly exceeds the number of observations.
An optimal tool to tackle the task may be based on machine learning algorithms, such as
collected in the "scikit-learn" Python module (see e.g., the "orthogonal matching pursuit"
algorithm.

The project is part of an ongoing active research of numerous open questions, such as
the identification of an optimal set of environmental parameters, the minimization of
the number of explanatory variables (compromise between practical use and accuracy),
or exploiting the capabilities of machine learning concepts.

# Tasks

## 1. Data acquisition

The collection of flowering dates is stored in Excel table and can be downloaded [here](http://lecso.elte.hu/downloads/V_KEZD_Excel_SORTED_cut.csv)
This is a comma separated CSV file with two header lines. The first column is related to
the number of individuals for a given species, the next 33 columns are the flowering dates
in units of "day of the year" (leap years are properly treated). Species are identified by the 
mean flowering date (mean value over the available time span), it is useful to standardize
everything.

Weather data can be downloaded from the ECMWF ERA-40 historical reanalysis data [bank](http://apps.ecmwf.int/datasets/data/era40-daily/levtype=sfc/)
Registration is necessary, please use a university e-mail (instead of google or yahoo),
please read the [instructions](https://confluence.ecmwf.int/display/WEBAPI/Access+ECMWF+Public+Datasets) for mass data acquisition, too (e.g. by Python scripts).
Please collect candidate data from the "Surface" parameter set, the location of the garden is
Budapest, Hungary, 47.4413°N, 19.0179°E. A few neighboring sites are enough for
the period of 1967 (one year before the first flowering records) to 2000, such as:
2 metre temperature  (or)
Skin temperature
Evaporation 
Soil temperature, level 1 - 4
Surface solar radiation downwards 
Volumetric soil water, layer 1 - 4, etc.
The "parameter" database is at this [link](http://apps.ecmwf.int/codes/grib/param-db)

## 2. Fit of flowering date fluctuations

The next step is to play around with an explanation of the year-to-year fluctuations of 
flowering days depending on the weather history. Meaningful parameters are, e.g.,
L : length of climate history backward in time from flowering (up to 200-300 days).
N: number of environmental parameters
n: number of required nonzero parameters
In order to understand the last parameter, please learn about the "orthogonal matching pursuit" 
(OMP) algorithm. OMP is a sparse approximation procedure which aims to find the „
"best matching" projections of multidimensional data onto an over-complete (redundant) 
set of independent variables.
Please note that a proper variable set contains  weakly correlated weather signals (e.g., 
temperature values in the soil layers 1 - 4 are strongly correlated, thus incorporating
each of them is very ineffective).

## 3. Test the efficiency of predictions

Divide the date sets into two slices, as usual (learning/test sets, e.g. the learning phase is
the first 20-30 years, and test the remaining 5-6 years for predictions). Please note that
the records for the species are not homogeneous, missing data (missing years) should 
be handled properly. Test the stability of explanatory fits by changing the length of learning
set (e.g. from 20 to 27 years, where it is available), and test the power of predictability
by comparing recorded and extrapolated flowering dates.



