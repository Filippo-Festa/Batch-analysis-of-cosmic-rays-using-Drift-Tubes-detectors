# Batch analysis of cosmic rays using Drift Tubes detectors

Final project for the course *Management and analysis of physics dataset - module B*. 
\
The course focuses on:
1. **Data Management**
\
Data structures; Storage Models; Reliability; Availability; Authentication and Authorization; Local and Distributed File systems; Cloud storage; Databases


2. **Data processing**
\
Parallel processing; Distributed Computing Systems and the Grid paradigm; Cloud computing service models; Virtualization; Containerization; Hadoop as a paradigm for big data processing; Data processing with Spark; Data processing with Dask; Kafka as a distributed streaming platform



## Analysis of real data collected in a particle physics detector to reconstruct the trajectory of muons from cosmic rays.
&nbsp;
A set of muon detectors have been built and installed in Legnaro INFN Laboratories and are currently used to collect signals from cosmic rays.
The working principles of these detectors (named mini Drift Tubes or miniDTs) are based on ionization: charged particles traversing the volume of the detectors will ionize the
gas mixture inside, thus producing electron-ion pairs. Specifically shaped electric fields make the electron cloud travel throughout the volume with an almost constant drift velocity
$(v_{drift} = 53.8 \\mu m/ns)$. Close to a sensing anode wire, the intense electric field will produce further ionization and avalanche, thus increasing the signal gain.
Signals are collected on the anodic wire, then amplified, digitized, discriminated, and sent through a DAQ system where a set of FPGAs perform the Time-to-Digital Conversion
(TDC): to each electron cloud reaching the wire a digital signal is associated corresponding to the time of collection.
Each digitized signal is commonly referred to as an “hit”.

<p align="center">
<img src="https://github.com/MarijaMojsovska/MAPD-Project/blob/main/image1.png">
</p>

If the time of passage of the muon (usually referred to as $t_{0}$) is known, the TDC of a hit can be translated to a position inside the cell thanks to the constant $v_{drift}$, i.e.:

<p align="center">
$x_{hit} = (t_{hit} - t_{0})v_{drift}$
</p>

The time of the passage of the muon is however not generally known a priori and must be extracted from external information (or geometrical considerations).
Furthermore, an intrinsic left-right ambiguity is associated with the time-to-space conversion: the time information of a single hit is not enough to discriminate whether the
muon passed in the right- or left-half of the cell. A full reconstruction of a track spanning multiple cells is necessary to solve the ambiguity
and identify the track trajectory throughout 1 or more DT chambers.

The geometry of one single detector (a miniDT “chamber”) is composed of 64 cells arranged in 4 layers of 16 cells each. Adjacent layers are staggered by half of a cell width.
Each cell has a transversal dimension of 42 x 13 $mm^{2}$ (width x height). The schema for one DT chamber is reported in the following figure:

<p align="center">
<img src="https://github.com/MarijaMojsovska/MAPD-Project/blob/main/image2.png">
</p>

Four DT chambers are stacked on top of each other in a “muon-telescope” configuration, where 3 chambers (0,2,3) are in the same orientation, and the fourth (1) is rotated 90
degrees to measure in the orthogonal view.

Two external detectors (plastic scintillator palettes, in blue in the figure) provide the external timing information for the particle passage, hence the $t_{0}$ information.

<p align="center">
<img src="https://github.com/MarijaMojsovska/MAPD-Project/blob/main/image3.png">
</p>

## Group members
- [Filippo Orlando](https://github.com/Filorland)
- [Marija Mojsovska](https://github.com/MarijaMojsovska)
- [Filippo Festa](https://github.com/Filippo-Festa)
- [Andrea Peri](https://github.com/periandrea)
