---
title: "Data Analysis of Coal Fly Ash"
categories: portfolio
layout: single
---

This project started as a way to get automatic emails when the waves near Bellingham look good for surfing. The model updates every 15 minutes, sends out an email if need be, and creates a historical archive for the eventual training of a stochastic model. Please contact me if you want to be on the automatic email serve (~5 emails a month in the winter). 

There are currently no public ocean wave models built to represent the bathymetry of the Salish Sea. My [Salish Sea Surf Report](https://github.com/GavinScoville/Buoy-Proj/blob/main/Salish-Surf-Report.md) is a bare-bones model, updated every 15 minutes. As of this post, it follows the path of waves across the Pacific using spherical trigonometry. It then applies a refraction model for waves entering the Salish Sea, using ray tracing to identify regions of convergence and divergence. Below are example maps from Nov 12, 2025. 

**Current limitations include:**

No diffraction  
No nonlinear wave interactions  
Wave data is monochromatic — only dominant period, significant wave height, and mean direction are available; full spectral data is not currently accessible. 
No Coriolis effect  
No Doppler shifting from currents and no wind–wave interactions  

**Next Steps:**  
My next goal is to build a wave model capable of simulating multi-spectrum wave–wave interactions, diffraction, and refraction using PDEs. Maybe on a Geodesic grid. It might be a while…

[See the most recent Salish Sea Surf Report ->](https://github.com/GavinScoville/Buoy-Proj/blob/main/Salish-Surf-Report.md)

"{{ site.baseurl }}/assets/images/Bowl_Shape.png"