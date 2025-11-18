---
title: "Salish Sea Surf Report"
categories: portfolio
layout: single
---

There are currently no publicly available wave models representing the bathymetry of the Salish Sea. The [Salish Sea Surf Report](https://github.com/GavinScoville/Buoy-Proj/blob/main/Salish-Surf-Report.md) is updated every 15 minutes. As of this post, it follows the path of waves across the Pacific using spherical trigonometry. It then applies a refraction model to waves entering the Salish Sea, utilizing ray tracing to identify regions of convergence and divergence. Below are example maps from Nov 12, 2025.

<img src="{{ site.baseurl }}/assets/images/pacific.png" alt="Wave Path in the Pacific"/> 

1,600 km off the west coast, the Ocean Papa buoy picks up wave data. Using the dominant period duration, mean wave direction, and significant wave height, we can infer the trajectory and phase speed of waves as they move across our spherical Earth. 

<img src="{{ site.baseurl }}/assets/images/Strait.png" alt="Waves Refracting in the Strait"/>

At the mouth of the Salish Sea, a Neah Bay buoy gives us monochromatic wave data. This is a ray-tracing diagram to show how these simplified waves refract as they move across the bathymetry. My model uses a limited algorithm to predict wave height by holding energy flux constant.

<img src="{{ site.baseurl }}/assets/images/Island.png" alt="Waves Refracting in the Islands"/> 

Using the same algorithm, the rays in this wave map are a linear interpolation of the waves from the Port Angeles Buoy to the New Dungeness Buoy.

**Current limitations include:**

- No diffraction  
- No nonlinear wave interactions  
- Wave data is monochromatic — only dominant period, significant wave height, and mean direction are available; full spectral data is not currently accessible.  
- No Coriolis effect  
- No Doppler shifting from currents and no wind–wave interactions  

**Next Steps:**  
My next goal is to build a wave model capable of simulating multi-spectrum wave–wave interactions, diffraction, and refraction using Navier–Stokes equations. Maybe on a geodesic grid. It may be a while.

**Email List Serve**  
This project started as a way to get automatic emails when the waves near Fort Ebey look good for surfing. The model updates every 15 minutes, sends out an email if need be, and creates a historical archive of training data. Please contact me if you want to be on the automatic email list serve (~5 emails a month in the winter). 

[See the most recent Salish Sea Surf Report ->](https://github.com/GavinScoville/Buoy-Proj/blob/main/Salish-Surf-Report.md)
