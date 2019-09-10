# Cell motion

In this project based on the work of Levine et al. and Zamir et al 
you will analyse 
motion of a human glioblastome cell culture.

- Link to the Levine et al. paper: [www](http://www.cim.mcgill.ca/~levine/live_cell_image_segmentation.pdf) 
- Link to the Zamir et al. paper: [www2](https://link.springer.com/article/10.1007%2Fs10439-005-3037-7)

### Introduction 

The dataset provided by the Czirok-Lab (ELTE) contains phase-contrast
microscopic time-lapse pictures of a cell culture. The pictures were taken
every 10 minutes. The picture names encode the experimental setting:
The first character of the name describes the cell-density
(A: 300 1/cm^2, B: 1000 1/cm^2, C:3000 1/cm^2, D: 10000 1/cm^2).
The second character (A,B,C) denotes the ring in the Petri-dish and
the number indicates the view within a ring (1,2,3,4).
For further details please refer to Fig. 6 in [publ](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0203203)

### Tasks

#### 1. Data exploration 
Find individual cells with image segmentation. The usual method is a
sliding window approach, where the variance is tresholded for meaningful
results. See the reference of Levine et al above.

#### 2. Measure velocity of cells

Based on the work of Zamir et al (see above), find the time evolution of 
velocity of each identified cells and estimate the velocity distribution.

#### 3. Try to fit an anomalous diffusion model model to the measured data!

## Dataset
Available [here](https://kooplex.vo.elte.hu/ownCloud/s/KsIA1NU0IDEigGZ) 1.7Gb
