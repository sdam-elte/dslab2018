# Scaling in turbulence

In this project based on the work of Elsas et al. (2018) you will analyse large scale hydrodynamical simulations datasets and investigate power-law scaling of high-order moments of velocity increments (structure functions) and dissipation rates.

- Link to the Elsas et al. (2018) paper: Elsas, J.H., Szalay, A.S. and Meneveau, C., 2018. Geometry and scaling laws of excursion and iso-sets of enstrophy and dissipation in isotropic turbulence. Journal of Turbulence, 19(4), pp.297-321. [JoT](https://www.tandfonline.com/doi/full/10.1080/14685248.2018.1424995) [arxiv](https://arxiv.org/abs/1708.05409)   

### Introduction 
(excrept from the Elsas et al. 2018 paper)

Dissipation rate and enstrophy have been observables of great interest in turbulence research due to their dynamical significance for the evolution of flow and their rich spatial structure and intermittent nature. In a view dating back to Kolmogorov and Obukhov, the transfer of kinetic energy from large to small scales proceeds as a self-similar cascade process accompanied with increasing intermittency of intense events, and these are often associated with large values of dissipation rate and enstrophy. The presence of power-laws in the velocity spectrum, velocity structure functions and moments of velocity gradients and dissipation are seen as an indication of such self-similar behaviour.

### The JHU Turbulence Database (JHTDB)

The Johns Hopkins University has a multi-Terabyte turbulence simulation database accessible. The various simulations include 
space-time history of a direct numerical simulation (DNS) of isotropic turbulent flow in incompressible fluid in 3D (100 Terabytes), a DNS of the incompressible magneto-hydrodynamic (MHD) equations (50 Terabytes), a DNS of forced, fully developed turbulent channel flow at Re=1000 (130 Terabytes), a DNS of homogeneous buoyancy driven turbulence (27 Terabytes), and a transitional boundary layer flow (105 Terabytes). Also available are individual snapshots (spatially but not temporally resolved data) of 4096^3 DNS of isotropic turbulence (1 snapshot) and rotating stratified turbulence (5 snapshots, 5 Terabytes), and channel flow at Reτ=5200 (11 snapshots, 20 Terabytes).

The database is cleverly indexed for efficient access through SQL, web services, C, Fortran, Matlab, Python. From individual particle tracking to evaluation of velocity and pressure at arbitrary points and time is supported using interpolations executed on the database nodes, avoiding high data volume downloads.  

There are large number of (publications)[http://turbulence.pha.jhu.edu/publications.aspx] listed at the portal both articles on the database architecture and research studies using the database. 

- Link to the [JHU Turbulence Database](http://turbulence.pha.jhu.edu/)
- [Python](https://github.com/idies/pyJHTDB) pyJHTDB packages for turbulence data access and processing 
- [SciServer](http://www.sciserver.org) for on site cloud support for data access through Jupyter notebooks (registration required) 

### Tasks

#### 1. Data exploration 
Register to SciServer and familiarize yourself with the datasest through the tutorials at the [pyJHTDB git repo](https://github.com/idies/pyJHTDB) and the [JHTDB](http://turbulence.pha.jhu.edu/tutorial.aspx). 

#### 2. Understanding scaling behaviour in turbulent flows
Read the [Elsas et al.](https://www.tandfonline.com/doi/full/10.1080/14685248.2018.1424995) paper. Understand the basic concepts and quantities, the role of dissipation and scaling. Explore the fractal analysis methods, the excursion sets, correlation function-based scaling, box-counting dimensions based on the cited and other background materials.

#### 3. Power-law analysis of turbulence simulation data 
Follow the guidelines in the paper and reproduce the scaling results with the various methods (Fig. 2,3) and its dependence on various parameters and ranges (Fig. 5,6) and optionally other results. 

#### 4. Your own ideas on other analyses are also welcome!



