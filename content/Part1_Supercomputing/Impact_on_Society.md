# The impact of supercomputing on society 
<!-- Should I edit the wording to make the research more accessible, or is it okay to leave as high-level examples?-->

Supercomputing has a significant impact on society in various ways. Let's have a look at some of the key ways. 

Throughout this part you will see images from the ARCHER2 community. [ARCHER2](https://www.archer2.ac.uk/) is the UK National Supercomputing Service, it is a world class advanced computing resource for UK researchers. ARCHER2 is provided by UKRI, EPCC, HPE Cray and the University of Edinburgh.

<!-- Can we just use these? https://www.archer2.ac.uk/research/case-studies/ -->

## Advancing Scientific Research: 

Supercomputers enable complex simulations and calculations that help scientists make breakthroughs in fields like physics, chemistry, biology, and climate science. They accelerate research and lead to discoveries that can improve human understanding of the world.

```{figure} ./images/53193849353_6e2e01c4c2_c.jpg
```

**The shining stars of turbulence by Juan Carlos Bilbao-Ludena, Imperial College London, Deparment of Aeronautics**

This image captures the transformation of a two-dimensional-like shear layer, depicting its journey starting from structured order. Initially, the shear layer appears as an elongated singular shape, but as it undergoes in-viscid fragmentation, it breaks down into smaller sizes, where dissipation levels are present leading into what is known as fully developed turbulence. The bright contrasting contours in the image showcases the levels of linkage between different length scales in the flow. The present simulation was obtained with the parallel code Pantarhei on Archer2, which enable us to reveal new flow physics with the accuracy that is needed.



## Engineering and Design: 

Supercomputing plays a crucial role in engineering and design processes. It allows engineers to simulate and test complex systems, such as aircraft designs, bridges, and energy systems, before physical prototypes are built. This reduces costs, improves safety, and drives innovation.

## Medical and Healthcare: 

Supercomputing aids in medical research, drug discovery, and personalized medicine. It enables researchers to analyze vast amounts of genomic data, simulate the behavior of biological systems, and develop more effective treatments for diseases.

<iframe width="700" height="400" src="https://youtu.be/_Lt5VcpAF7U" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<!-- https://youtu.be/_Lt5VcpAF7U -->

**Silico model for assessing individual responses to irregular heart rhythm treatments, by Carlos Edgar Lopez Barrera, Queen Mary University of London, SEMS**

This video demonstrates the creation of a personalized in silico model for assessing individual responses to irregular heart rhythm treatments. These customized computational models can predict how a patient will react to therapy and facilitate virtual trials. The process starts with a point cloud extracted from a segmented MRI scan, providing a spatial representation of the atrium. These points are interconnected to form a 3D finite element mesh that reflects the patient's unique anatomy. The cardiac tissue's directional properties, influenced by atrial fiber orientation, are incorporated from a DT-MRI atlas. The model then simulates electrical activity and electrograms using the openCARP solver to explore irregular heart rhythms like atrial fibrillation. Post-simulation analysis identifies critical atrial fibrillation regions. Procedures like radiofrequency catheter ablation or anti-arrhythmic drug administration can be virtually tested to predict the patient's individualized response, as demonstrated in this case with pulmonary vein isolation ablation therapy.

```{note}

This is the Winning Early Career Researcher entry from 2023! 

```


## Weather Forecasting and Climate Modeling: 

Supercomputers play a vital role in weather prediction and climate modeling. They help meteorologists understand and forecast severe weather events, track hurricanes, and study long-term climate patterns. Accurate weather predictions are crucial for disaster preparedness and climate change mitigation. 

<iframe width="700" height="400" src="https://youtu.be/YXL5Vu046wU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

**The Galewsky Jet with a moving mesh by Dr Jack Betteridge, Imperial College London, Mathematics**

This video shows a simulation of a jet stream around the North Pole over the period of one week. The rotating shallow-water equations are solved on the surface of a sphere, using the same numerical methods that are used in the Met Office’s next-generation weather forecasting model. In this animation, the mesh moves, with the resolution adapting to the gradient of the vorticity field. This allows the computational resources to be concentrated to the most complex features of the fluid. The shaded region shows the vorticity of the fluid, while the arrows show the size and direction of the wind. The contours show the streamlines along which the fluid flows. 
*Surface of the Earth photograph image credit: NASA - Visible Earth Blue Marble: Land Surface, Shallow Water, and Shaded Topography. Copyright information from https://visibleearth.nasa.gov/image-use-policy*


<iframe width="700" height="400" src="https://youtu.be/owr3svmN0p8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

**Fine-scale numerical system for prediction nearshore upwelling in Canaria Basin and carbon removal, 3D animation of temperature distribution by Dr Dmitry Aleynik and Dr Max Holloway, SAMS**

The coupled atmosphere-ocean circulation model of the Canary Current Upwelling System predicts the timing and position of filaments and stripes of colder seawater enriched with higher levels of dissolved nutrients over five days. The intake seawater pipes are feeding a prototype novel sustainable protein farm located in a desert area near the coast. An unstructured Finite-Volume Coastal Ocean Model with unprecedented resolution (100m) allows assessment of the dispersion of de-acidified water discharged from shallow basins, where dissolved carbon dioxide is naturally consumed by growing microalgae. The ponds are the size of a football pitch, expected to scale up to 1000ha. Physical oceanographic measurements over different seasons helped to calibrate and then evaluate the accuracy of model predictions. Development of the weather (WRF) and ocean (FVCOM) components of the regional hydrodynamic modelling system, test runs on ARCHER2 HPC and visualization (cooperation with M.Holloway) were supported by Innovate-UK (Agri-SATT grant) and NERC.



## Energy and Environment:  

Supercomputing supports the development of renewable energy sources, optimization of energy systems, and environmental modeling. It helps researchers analyze and simulate complex energy systems, improve energy efficiency, and study the impact of human activities on the environment.

## Data Analysis and Artificial Intelligence: 

Supercomputing facilitates big data analysis and accelerates artificial intelligence (AI) research. It enables the processing of massive datasets, training of AI models, and development of innovative AI applications in various fields, including finance, healthcare, and transportation.

---

Overall, supercomputing has a transformative impact on society by driving scientific progress, enabling advanced simulations and calculations, and addressing complex societal challenges across multiple domains.