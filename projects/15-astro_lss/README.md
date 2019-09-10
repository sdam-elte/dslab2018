# Visualize the large scale structure of the universe in a full dome planetarium

The large scale structure of the universe, also called the cosmic web, is a very distinctive distribution of galaxies determined by the evolution of dark matter density due to gravity. Galaxies are located in _filaments_, _walls_ and _superclusters_ which surround _voids_, vast volumes of empty space. Below is a _slice_ of the cosmic web drawn from the data collected by the Sloan Digital SkySurvey

![](img/orangepie.jpg)

This is, however, just a slice. The goal of the project is to visualize the depth and celestial extent of the data set. An example is the fly-through animation created by Aragon-Calvo et al. (2012) which is obviously beyond the scope of this project.

* Link to SDSS fly-through video: https://www.youtube.com/watch?v=08LBltePDZw

A feasible visualization project is to cut up SDSS data into redshift shells, project galaxies marked with dots in these shells after each other to the dome with some smart coloring to archieve a fly-through effect.

## Sloan Digital Sky Survey

The Sloan Digital Sky Survey (sometimes also called the Cosmic Genome Project) is a systematic photographic and specroscopic mapping of the extragalactic universe. During the first phase of the project, an imaging survey was conducted to photograph the sky in five optical wavelength band with a 120 megapixel camera. It was followed by a spectroscopic survey where more than 2 million objects, including more than a million galaxies were observed with a multi-fiber spectrograph.

The SDSS catalog (numerical parameters of the detected objects extracted from the multi-band images) is available as a relational database via SkyServer.

* Link to SDSS SkyServer: http://skyserver.sdss.org/

## Full dome projection

Digital planetarium systems use high resolution projectors to visualize the night sky. Modern planetariums are equipped with multiple high resolution beamers but spectacular visualization with single projector theaters, like the one at ELTE, can also be achieved. Planetarium systems with a single projector use a fisheye converter lens to distort the originally rectangular image onto the dome.

* Wikipedia on fisheye lens: https://en.wikipedia.org/wiki/Fisheye_lens

## Tasks

### 1. Data acquisition

Register to SDSS SkyServer and collect the necessary data from the SDSS DR7 main galaxy sample. Preferably use the database to compute the absolute magnitudes. You will need the `PhotoObj` table to get the magnitude `petro_r` and the `SpecObj` table to get the redshift `z`. The join between the two tables can be made with `PhotoObj.objID = SpecObj.bestObjID`. Functions are provided for cosmological distance calculation.

### 2. Implement the projection

Find the right python package or develop the necessary function to plot data with stereographic or ortographic projection (depending on the planetarium system). Test it by projecting a grid.

### 3. Fly-through animation
