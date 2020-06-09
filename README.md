# uwa-channel-model

This repository contains the code to accompany the following publication:

N. Morozs, W. Gorma, B. Henson, L. Shen, P. D. Mitchell and Y. V. Zakharov, "Channel Modelling for Underwater Acoustic Network Simulation," in TechRxiv (submitted to IEEE Communications Surveys & Tutorials, Feb 2020).

This work was supported by the UK Engineering and Physical Sciences Research Council (EPSRC) through the USMART Project under Grant EP/P017975/1.

This code is published under the MIT License (see full license in the 'LICENSE' file)

******************************
## Prerequisites and installation

Required software:

1) MATLAB (tested on R2015a, R2018b and R2019a)
2) BELLHOP (part of Acoustics Toolbox: https://oalib-acoustics.org/AcousticsToolbox/)
   - The version used in our work (downloaded 17 Feb 2020, last modified 6 Jul 2018) 
   - The installation requires a FORTRAN compiler (e.g. _gfortran_ on Linux-based systems)
   - Please consult the _index.htm_ file at the Acoustics Toolbox root directory and the _bellhop-installation-notes.pdf_ provided by us for BELLHOP installation instructions

********
## Contents

The list of subdirectories:

- __channel_model__: MATLAB files and data referenced in Sections IV and V of the tutorial paper. All of the channel modelling code is inside this folder.

- __riverbed_case_study__: the data, results and the plotting script for the Riverbed Modeler single-hop ALOHA case study (Section VI.A)

- __stdma_case_study__: simulation scripts, channel data and results for the statistical channel modelling and STDMA case study (Section VI.B)

- __north_sea_linnet_study__: channel modelling, simulation and plotting scripts for the North Sea simulation study (not part of the tutorial: linear network, STDMA, January vs July)


The descriptions of the MATLAB scripts and functions in the __channel_model__ subdirectory can be accessed by typing ``help <script/function name>`` into the MATLAB console. Their functionality are also described in the paper. Below is a list of some of the key scripts performing various channel modelling tasks described in the paper. Note, the results may vary slightly compared to those included in the paper, since the random number generator may produce different sea surface/bottom realizations and node position permutations on different versions of MATLAB.

- ``single_sim``: this is the best starting point to familiarize yourself with our model. It performs a single ray tracing simulation and produces plots in Fig. 2, 3, 4, 7, 9, 10, depending on the specified type of simulation.

- ``create_grid_lut``: this script runs BELLHOP on a grid of receiver depths and ranges and generates raw channel impulse response data used for Figures 11 and 13.

- ``plot_rxp_snr_grids``: this script produces the contour plots as in Fig. 11 and 13, using the data generated by the script above.

- ``example_3d_channel_lut_gen``: this script creates a channel look-up table (raw or processed) for a given set of node positions in 3D space. This was the script we used to generate the data for the Riverbed Modeler case study described in Section VI.A of the paper.

- ``example_stat_channel_model``: this script generates a statistical channel model for a specified pair of source-receiver positions described in Subsection V.C. It also produces the graphs from Fig. 17 and 18.

- ``create_stat_ch_model_linnet``: this script generates a statistical channel model for the linear network case study in Subsection VI.B of the paper.

