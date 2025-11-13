---
title: "The Salish Sea Surf Report"
categories: portfolio
layout: single
date: 2024-11-23
markdown: kramdown
---


<img src="/assets/images/pacific.png" alt="Wave Path in the Pacific">

1,600 km off the coast, the Ocean Papa bouy picks up wave data. Using this data we can infer the trajectory of waves as they move across our spherical earth.

<img src="/assets/images/Strait.png" alt="Waves Refracting in the Strait">
At the mouth of the Salish Sea, a Neah Bay bouy gives us monocromatic directional wave data. This ray-tracing diagram is a heuristic model to show how the coastline will bend and refract waves at different wavelengths and directions. Right now there is a cheesy algorythm to predict wave height by holding energy flux between the rays constant.


<img src="/assets/images/island.png" alt="Waves Refracting in the Islands">
Using the smae algorythem, the rays in this wave map are a linear interpolation of the waves from the Port Angelis Bouy to the New Dungeness Bouy. 


There are currently no public ocean wave models built to represent the bathymetry of the Salish Sea. My **Salish Sea Surf Report** is a modest model, updated continiously. As of this post, it follows the path of waves across the Pacific using spherical trigonometry. It then applies a refraction model for waves entering the Salish Sea, using ray tracing to identify regions of convergence and divergence. 

The model updates every 15 minutes and creates a historical archive for eventual training of a stochastic model.

**Current limitations include:**

A) No diffraction  
B) No nonlinear wave interactions  
C) Wave data is monochromatic — only dominant period, significant wave height, and mean direction are available; full spectral data is not currently accessible. 
D) No Coriolis effect  
E) No Doppler shifting from currents and no wind–wave interactions  

**Next Steps:**  
My next goal is to build a wave model capable of simulating multi-spectrum wave–wave interactions, diffraction, and refraction using PDEs. Maybe on a Geodesic grid. It might be a while…



[See the most recent Salish Sea Surf Report ->](https://github.com/GavinScoville/Buoy-Proj/blob/main/Salish-Surf-Report.md)
