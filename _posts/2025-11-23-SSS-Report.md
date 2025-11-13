---
title: "The Salish Sea Surf Report"
categories: portfolio
layout: single
date: 2025-11-23
---

This project started as a way to get automatic emails when the waves near Bellingham look good for surfing. The model updates every 15 minutes, sends out an email if need be, and creates a historical archive for the eventual training of a stochastic model. Please contact me if you want to be on the automatic email serve (~5 emails a month in the winter). 

There are currently no public ocean wave models built to represent the bathymetry of the Salish Sea. My [Salish Sea Surf Report](https://github.com/GavinScoville/Buoy-Proj/blob/main/Salish-Surf-Report.md) is a bare-bones model, updated every 15 minutes. As of this post, it follows the path of waves across the Pacific using spherical trigonometry. It then applies a refraction model for waves entering the Salish Sea, using ray tracing to identify regions of convergence and divergence. Below are example maps from Nov 12, 2025. 

<img src="/assets/images/pacific.png" alt="Wave Path in the Pacific"/>

1,600 km off the west coast, the Ocean Papa bouy picks up wave data. Using the dominant period duration, mean wave direction, and significant wave height, we can infer the trajectory and phase speed of waves as they move across our spherical earth.

<img src="/assets/images/Strait.png" alt="Waves Refracting in the Strait"/>

At the mouth of the Salish Sea, a Neah Bay bouy gives us monocromatic directional wave data. This ray-tracing diagram is a heuristic model to show how the coastline will bend and refract waves at different wavelengths and directions. Right now there is a limited algorithm to predict wave height by holding energy flux between the rays constant.


<img src="/assets/images/Island.png" alt="Waves Refracting in the Islands"/>

Using the same algorithm, the rays in this wave map are a linear interpolation of the waves from the Port Angelis Bouy to the New Dungeness Bouy. 

**Current limitations include:**

A) No diffraction  
B) No nonlinear wave interactions  
C) Wave data is monochromatic — only dominant period, significant wave height, and mean direction are available; full spectral data is not currently accessible. 
D) No Coriolis effect  
E) No Doppler shifting from currents and no wind–wave interactions  

**Next Steps:**  
My next goal is to build a wave model capable of simulating multi-spectrum wave–wave interactions, diffraction, and refraction using PDEs. Maybe on a Geodesic grid. It might be a while…

[See the most recent Salish Sea Surf Report ->](https://github.com/GavinScoville/Buoy-Proj/blob/main/Salish-Surf-Report.md)

