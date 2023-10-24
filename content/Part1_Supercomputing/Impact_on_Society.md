# The Impact of Supercomputing on Society 
<!-- Should I edit the wording to make the research more accessible, or is it okay to leave as high-level examples?-->
<!-- Should we rename this? -->

Supercomputing has a transformative impact on society by driving scientific progress, enabling advanced simulations and calculations, and addressing complex societal challenges across multiple domains. Let's have a look at some examples. 

```{note}
All of these images are from the ARCHER2 community! [ARCHER2](https://www.archer2.ac.uk/) is the UK National Supercomputing Service, hosted by EPCC at the University of Edinburgh.
```


<!-- Can we just use these? https://www.archer2.ac.uk/research/case-studies/ -->

## Advancing Scientific Research: 

Supercomputers enable complex simulations and calculations that help scientists make breakthroughs in fields like physics, chemistry, biology, and climate science. They accelerate research and lead to discoveries that can improve human understanding of the world.

```{figure} ./images/53183414945_4f209c79a1_c.jpg 
```

**Late-time drop breakup interacting with uniform surrounding airflows, by Kaitao Tang, Department of Engineering Science, University of Oxford**

We conduct high-resolution direct numerical simulations investigating the deformation and breakup of liquid drops interacting with uniform ambient airflows. The morphology of the drop before its breakup is governed by a competition between inertial and capillary forces; and in our regime of interest, the droplet deforms into a thin bag film attached to a toroidal rim. A recently developed numerical algorithm is applied to artificially create holes on the thin bag film and initiate its fragmentation, so that the resulting liquid drop statistics are not dependent on the grid size. The image shows the film breakup process with this algorithm applied, where one can observe the expansion of holes on the film, the formation of liquid ligaments following the merge two hole rims, and the subsequent breakup of the ligaments producing droplets with different sizes, which often experience shape oscillations.


```{figure} ./images/53193849353_6e2e01c4c2_c.jpg
```

**The shining stars of turbulence by Juan Carlos Bilbao-Ludena, Imperial College London, Deparment of Aeronautics**

This image captures the transformation of a two-dimensional-like shear layer, depicting its journey starting from structured order. Initially, the shear layer appears as an elongated singular shape, but as it undergoes in-viscid fragmentation, it breaks down into smaller sizes, where dissipation levels are present leading into what is known as fully developed turbulence. The bright contrasting contours in the image showcases the levels of linkage between different length scales in the flow. The present simulation was obtained with the parallel code Pantarhei on Archer2, which enable us to reveal new flow physics with the accuracy that is needed.

```{figure} ./images/52371640626_5b6363d9f2_c.jpg
```

**Expiratory particle dispersion by turbulent exhalation jet during speaking, by Aleksandra Monka, University of Birmingham, Department of Civil Engineering**

The image reveals the extent of expiratory particle dispersion by the turbulent exhalation jet during speaking, with this high-resolution simulation run on the ARCHER2 system. A 3D overview figure of the whole room is shown in the bottom right-hand corner for spatial context. The particle’s ability to stay airborne is affected by its diameter: the largest particles (red and yellow) fall out close to the speaking person, while the smaller ones (blue) are entrained into the exhalation jet and transported throughout the room. The aim of the research is to develop a numerical tool to predict accurately the spread of airborne pathogens carried by very small expiratory particles in different indoor environments. The novelty of this work lies in the ability to determine and quantify the spatiotemporal distribution of airborne pathogens and the infection risk in different indoor scenarios, considering the turbulent mixing of particles on their spread.

```{note}

This is the winning image entry from the 2022 ARCHER2 competition and the overall winner! 

```

## Engineering and Design: 

Supercomputing plays a crucial role in engineering and design processes. It allows engineers to simulate and test complex systems, such as aircraft designs, bridges, and energy systems, before physical prototypes are built. This reduces costs, improves safety, and drives innovation.

```{raw} html
<iframe width="560" height="315" src="https://www.youtube.com/embed/TpClNdfnkn4?si=rTzsJgaQvvAlP98Q" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
```

**Unsteady Flow Over Random Urban-like Obstacles: A Large Eddy Simulation using uDALES 2.0 Codebase by Dr Dipanjan Majumdar, Imperial College London, Civil and Environmental Engineering Department**

uDALES stands as an open-source large-eddy simulation framework, specifically designed to tackle unsteady flows within the built environment. It is capable of simulating airflow, sensible and latent heat transfer, and pollutant dispersion within the urban atmospheric boundary layer. The simulation framework adopts the immersed boundary method to resolve buildings, supplemented with wall functions to account for surface shear stresses and heat fluxes. Additionally, a three-dimensional surface energy balance model establishes a two-way coupling, accommodating both man-made and vegetative materials. To achieve optimal performance, uDALES utilizes two dimensional domain decomposition, facilitating parallelization and resource utilization on supercomputers like ARCHER2 for exascale computing. The presented figure was generated while validating the latest version uDALES 2.0 against a classical study by Xie et al. (2008) on flow over random urban-like obstacles. It showcases the instantaneous stream-wise velocity contour at a spanwise plane intersecting the tallest building within the simulated domain.

```{figure} ./images/52720977651_28ffe1afbd_c.jpg  
```

**Delayed detached-eddy simulation of a large civil aircraft in transonic flow by Dr Sebastian Timme, University of Liverpool, Department of Engineering**

The image illustrates the phenomenon of shock buffet in the transonic flow around a large civil aircraft. The surface pressure distribution highlights the strong shock wave forming over the wings, acting to separate the boundary layer and resulting in large-scale turbulent eddies. Streamlines indicate the disturbed airflow in the wake behind the wings.

Understanding shock buffet is important in aircraft design as the resulting structural vibrations and unsteady aerodynamic loads limit the flight envelop. The data shown in the figure is the result of six coupled nonlinear equations solved at 29 million points for over 100,000 time steps. This enormous computational task would not have been possible without access to ARCHER through the EPSRC Resource Allocation Panel.


## Medical and Healthcare: 

Supercomputing aids in medical research, drug discovery, and personalized medicine. It enables researchers to analyze vast amounts of genomic data, simulate the behavior of biological systems, and develop more effective treatments for diseases.

```{figure} ./images/53104947273_1c81a1a854_c.jpg 
```

**Modelling proton tunnelling in DNA replication, by Max Winokan, University of Surrey, Quantum Biology DTC**

Proton transfer between the DNA bases can lead to mutagenic Adenine-Thymine tautomers. In our work, we determine that the energy required for generating tautomers radically changes during the separation of double-stranded DNA. Our results demonstrate that the unwinding of DNA by a helicase enzyme could significantly enhance the stability of tautomeric base pairs and provide a feasible pathway for DNA spontaneous mutations. This image shows the site of such a double proton transfer in a A-T base pair within the nucleic acid duplex. To produce the image atomic coordinates were taken from molecular dynamics simulations (Gromacs on Archer2) before being rendered in VMD. A Van der Waals envelope was added to show the atoms used in quantum chemical models. The image has been further altered in Photoshop to highlight the delocalised nature of the tunnelling proton. The quantum chemical calculations were performed with NWChem on Archer2.

```{note}

This is the winning image entry from the 2023 ARCHER2 competition and the overall winner! 

```


```{raw} html
<iframe width="560" height="315" src="https://www.youtube.com/embed/_Lt5VcpAF7U?si=npevHQ0u0SkozjNX" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
```
<!-- https://youtu.be/_Lt5VcpAF7U -->

**Silico model for assessing individual responses to irregular heart rhythm treatments, by Carlos Edgar Lopez Barrera, Queen Mary University of London, SEMS**

This video demonstrates the creation of a personalized in silico model for assessing individual responses to irregular heart rhythm treatments. These customized computational models can predict how a patient will react to therapy and facilitate virtual trials. The process starts with a point cloud extracted from a segmented MRI scan, providing a spatial representation of the atrium. These points are interconnected to form a 3D finite element mesh that reflects the patient's unique anatomy. The cardiac tissue's directional properties, influenced by atrial fiber orientation, are incorporated from a DT-MRI atlas. The model then simulates electrical activity and electrograms using the openCARP solver to explore irregular heart rhythms like atrial fibrillation. Post-simulation analysis identifies critical atrial fibrillation regions. Procedures like radiofrequency catheter ablation or anti-arrhythmic drug administration can be virtually tested to predict the patient's individualized response, as demonstrated in this case with pulmonary vein isolation ablation therapy.

```{note}

This is the winning Early Career Researcher entry from the 2023 ARCHER2 competition! 

```


## Weather Forecasting and Climate Modeling: 

Supercomputers play a vital role in weather prediction and climate modeling. They help meteorologists understand and forecast severe weather events, track hurricanes, and study long-term climate patterns. Accurate weather predictions are crucial for disaster preparedness and climate change mitigation. 

```{raw} html
<iframe width="560" height="315" src="https://www.youtube.com/embed/YXL5Vu046wU?si=Cjw0xLOV2NGz7zUO" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
```

**The Galewsky Jet with a moving mesh by Dr Jack Betteridge, Imperial College London, Mathematics**

This video shows a simulation of a jet stream around the North Pole over the period of one week. The rotating shallow-water equations are solved on the surface of a sphere, using the same numerical methods that are used in the Met Office’s next-generation weather forecasting model. In this animation, the mesh moves, with the resolution adapting to the gradient of the vorticity field. This allows the computational resources to be concentrated to the most complex features of the fluid. The shaded region shows the vorticity of the fluid, while the arrows show the size and direction of the wind. The contours show the streamlines along which the fluid flows. 
*Surface of the Earth photograph image credit: NASA - Visible Earth Blue Marble: Land Surface, Shallow Water, and Shaded Topography. Copyright information from https://visibleearth.nasa.gov/image-use-policy*

```{raw} html
<iframe width="560" height="315" src="https://www.youtube.com/embed/owr3svmN0p8?si=Kj9AxUIiY7j9UkuA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
```

**Fine-scale numerical system for prediction nearshore upwelling in Canaria Basin and carbon removal, 3D animation of temperature distribution by Dr Dmitry Aleynik and Dr Max Holloway, SAMS**

The coupled atmosphere-ocean circulation model of the Canary Current Upwelling System predicts the timing and position of filaments and stripes of colder seawater enriched with higher levels of dissolved nutrients over five days. The intake seawater pipes are feeding a prototype novel sustainable protein farm located in a desert area near the coast. An unstructured Finite-Volume Coastal Ocean Model with unprecedented resolution (100m) allows assessment of the dispersion of de-acidified water discharged from shallow basins, where dissolved carbon dioxide is naturally consumed by growing microalgae. The ponds are the size of a football pitch, expected to scale up to 1000ha. Physical oceanographic measurements over different seasons helped to calibrate and then evaluate the accuracy of model predictions. Development of the weather (WRF) and ocean (FVCOM) components of the regional hydrodynamic modelling system, test runs on ARCHER2 HPC and visualization (cooperation with M.Holloway) were supported by Innovate-UK (Agri-SATT grant) and NERC.



## Energy and Environment:  

Supercomputing supports the development of renewable energy sources, optimization of energy systems, and environmental modeling. It helps researchers analyze and simulate complex energy systems, improve energy efficiency, and study the impact of human activities on the environment.

```{raw} html
<iframe width="560" height="315" src="https://www.youtube.com/embed/FIjJiD-CmoQ?si=NqVwF9SNdwIHbfpk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
```

**Mirroring a Pyroclastic Flow Experiment using Large-Eddy Simulation, by Dr Eric Breard, School of Geoscience, University of Edinburgh**

The image and video are derived from a Large-Eddy Simulation of a pyroclastic flow, consisting of a hot mixture of air and particles that travel down an inclined channel before spreading across a flat terrain. The simulation mirrors one large-scale experiment conducted in New Zealand and is part of an international initiative to validate numerical models in Volcanology. Turbulent eddies, sedimentation, and vertical density stratification are depicted using the flow's free surface (split in half along the centerline), a vertical slice showing solid concentration, and a solid boundary rendered as glass. The domain encompasses 60 million cells, covering a volume of 28*6*5 m3. The multiphase flow simulation addresses the mass, momentum, and energy equations for all six phases (air plus 5 solid phases) and captures the granular to dilute turbulent regimes. The simulation was run using the US DOE's MFIX solver, utilizing 1200 CPU cores on ARCHER2 for 15 days.


```{note}

This is the winning video entry from the 2023 ARCHER2 competition! 

```


```{raw} html
<iframe width="560" height="315" src="https://www.youtube.com/embed/oXv9Yx5vzMM?si=Pa7cjauR201t_KA7" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
```

**Floating wind platform in wave by Dr Liang Yang and Dr Junxian Wang, Cranfield University, Energy and Sustainability**

Floating Offshore Wind Turbines (FOWT) play an important role in offshore renewable energy utilization, contributing to the net-zero target. This simulation conducts a preliminary study on the floating foundation of FOWT in regular waves using an open-source CFD tool (OpenFOAM-ESI). The built-in wave generation and overset mesh technique are adopted to create regular waves and handle the floater's dynamic response. The mesh near the floater (i.e., inner region), generated using meshing software ChopMesh, perfectly fits the structure's surface with excellent quality. Edges of the inner region match the structure's outline, ensuring a smooth transition.


<!-- ## Other/Summary/Question part(?)  -->