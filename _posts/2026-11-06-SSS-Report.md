---
title: "Salish Sea Surf Report"
categories: portfolio
layout: single
---

There are currently no publicly available wave models representing the bathymetry of the Salish Sea. The [Salish Sea Surf Report](https://github.com/GavinScoville/Buoy-Proj/blob/main/Salish-Surf-Report.md) is updated every 15 minutes. It is in development mostly as an educational tool for me to learn about both coastal processes and deterministic numerical modeling techniques. 

Models so far developed:

1,600 km off the west coast, the Ocean Papa buoy picks up wave data. Using the dominant period duration, mean wave direction, and significant wave height, we can infer the trajectory and phase speed of waves as they move across our spherical Earth: 

<img src="{{ site.baseurl }}/assets/images/pacific.png" alt="Wave Path in the Pacific"/> 

Ray tracing: A leapfrogged ray tracing method using Snell's law to understand more clearly how waves refract as they pass over shallow bathymetry. It was interesting, but unsatisfying, because it ignored diffraction entirely. The wave energy flux estimation is near-useless, and can contain singularities when rays cross each other at a location such as a point break. 

<img src="{{ site.baseurl }}/assets/images/Strait.png" alt="Waves Refracting in the Strait"/>

<img src="{{ site.baseurl }}/assets/images/Island.png" alt="Waves Refracting in the Islands"/> 


Wave equation: Using the wave equation, with variable celerity, to model diffraction and refraction of Airy waves (curvature in time = celerity squared × curvature in space) as they move through Salish Sea bathymetry. The model implements a finite difference and a leapfrogging scheme to propagate waves through time and space. This was interesting, and entertaining to watch. However, it left me unsatisfied because:
1) It could only run small grids quickly and with numerical stability. 
2) This model cannot incorporate shoaling, outside of an increased dampening coefficient in shallow water. 
3) The dampening coefficients are arbitrary, and I simply adjusted them until they looked mostly right. I have no training dataset to fit them to yet. 

<img src="{{ site.baseurl }}/assets/Salish_Sea_Surf/wave_simulation.gif" alt="Wave equation simulation of waves propagating through Salish Sea bathymetry"/>

Surface elevation rendered over the surrounding terrain (drag to rotate, scroll to zoom):

<iframe src="{{ site.baseurl }}/assets/Salish_Sea_Surf/wave_3d.html" title="Interactive 3D wave surface" width="100%" height="500" style="border:0;" loading="lazy"></iframe>

<a href="{{ site.baseurl }}/assets/Salish_Sea_Surf/wave_3d.html"><img src="{{ site.baseurl }}/assets/Salish_Sea_Surf/wave_3d.png" alt="3D render of modeled surface elevation along the coastline"/></a>

Mild Slope Spectral Methods: 
I am pulling NOAA Wavewatch III forecasts to use for future surf prediction. This is what every other surf forecasting website does as well. I am also trying to implement a mild slope spectral method, but I would like the opportunity to take higher level math courses to fully understand how to use a Laplace transform for solving the mild slope equation, and include refraction. It is also unsatisfying because of how it cannot implement dispersion. 

<img src="{{ site.baseurl }}/assets/Salish_Sea_Surf/mild_slope_simulation.png" alt="Mild slope simulation: significant wave height and Iribarren number breaker classification in the Strait of Juan de Fuca"/>

Acoustic Wave Forecast: 
If you multiply the frequency by 2^10 (10 octaves), a 12.5 second period wave is transformed to ~82 Hz, or a low E guitar string. Layering the different swells on top of each other into an acoustic surf forecast is fun, because you can hear the beats caused by similar frequencies. I think it is a more effective way to understand the consistency of a surf break. You can also hear swells from far away make landfall, where dispersion has caused the longer wavelength, longer period waves to travel ahead. Swells begin low pitched, and slowly climb upwards.

<audio controls preload="none" style="width:100%;">
  <source src="{{ site.baseurl }}/assets/Salish_Sea_Surf/salish_sea_whistle.mp3" type="audio/mpeg">
  <a href="{{ site.baseurl }}/assets/Salish_Sea_Surf/salish_sea_whistle.mp3">Listen to the acoustic surf forecast (MP3)</a>
</audio>

Eulerian Wave Model: 
Up next, I would like to build a finite volume Eulerian wave model, but I do not currently have time. 

Need for training data: 
I would like to implement stochastic modeling and machine learning techniques. However, I don't have any training datasets besides the difference between the buoy at Neah Bay and the buoy in Port Angeles. I am more interested in seeing how the waves will refract, diffract, and shoal rather than how they will propagate from one buoy to the next. 



[See the most recent Salish Sea Surf Report](https://github.com/GavinScoville/Buoy-Proj/blob/main/Salish-Surf-Report.md)
