---
layout: post
title: Design and Analysis of a Prototype RC Aircraft
description: An RC aircraft developed by a small team of individuals in an effort to more thoroughly understand important aircraft metrics. The design explores all relevant aircraft metrics, including the initial modeling, static stability, dynamic stability, and steady longitudinal flight.
skills: 
- CAD Modeling
- XFLR5
- Aircraft Analysis
- Prototyping
main-image: /prototypeRC.png
---

---
The goal of this project is to design an aircraft that is capable of flight. In the case of this project, successful performance metrics are defined as the aircraft's ability to maintain static stability, dynamic stability, and steady longitudinal flight.
## Initial Aircraft Modeling
By modeling the aircraft using XFLR5 and SolidWorks, a baseline set of parameters can be obtained that are essential for all of the calculations necessary. By using SolidWorks, it is possible to extract a simulated inertia tensor for the aircraft. These moments of inertia can then be input into XFLR5 to simulate the aircraft under an airspeed of 10 m/s.
{% include image-gallery.html images="cadaircraft.png" height="400"%}
<span style="font-size: 15px">SolidWorks Model of Aircraft and Inertia Tensor</span>
{% include image-gallery.html images="xflrsim.png" height="400"%}
<span style="font-size: 15px">Simulation using XFLR5</span>
<br>
The simulation results of XFLR5 can be seen below. These results will be the main method of sanity checking the aircraft's performance as the project develops.
{% include image-gallery.html images="xflrdragpolar.png" height="400"%}
<span style="font-size: 15px">Drag Polar Calculations of Aircraft from XFLR5</span>
{% include image-gallery.html images="xflrclcd.png" height="400"%}
<span style="font-size: 15px">Ratio of Cl and Cd as a Function of Angle of Attack</span>
## Static Stability Analysis
{% include image-gallery.html images="xflrcoefl.png, xflrcoefm.png" height="400"%}
<span style="font-size: 15px">Coefficients of Lift and Moment as a Function of Angle of Attack</span>
<br>
Static stability refers to the aircraft's ability to return to the initial equilibrium state after an external disturbance. This parameter is important to ensure random external forces do not result in the aircraft losing control. Static stability can be calculated by determining if the coefficient of moment has a negative slope with respect to the angle of attack. The initial calculations based on the physical prototype resulted in static instability. However, after adjusting the aircraft's elevator angles and applying these modifications to the initial XFLR5 simulations, a negative coefficient of moment slope was found.
## Dynamic Stability Analysis
Similar to static stability, dynamic stability also refers to an aircraft's ability to return to the initial equilibrium state after an external disturbance. Unlike static stability, dynamic stability must achieve equilibrium over a period of time. Because dynamic stability can apply to both longitudinal and lateral directions, both calculations must be made separately.
{% include image-gallery.html images="matlabdynamiclat.png, matlabdynamiclong.png" height="400"%}
<span style="font-size: 15px">Calculations of Dynamic Stability Using MATLAB (Left: Lateral, Right: Longitudinal)</span>
{% include image-gallery.html images="xflrdynamiclat.png, xflrdynamiclong.png" height="400"%}
<span style="font-size: 15px">Verification of MATLAB Calculation Using XFLR5 (Left: Lateral, Right: Longitudinal)</span>
## Steady Longitudinal Flight
The final performance criteria for this project is to identify the aircraft's performance in steady longitudinal flight. To conduct this analysis, a flight envelope can be constructed to find the upper and lower bounds of steady longitudinal flight. In order to create an accurate flight envelope, a few parameters must be collected: The minimum and maximum velocities as well as the stall velocities. The minimum and maximum velocities can be obtained using the minimum and maximum dynamic pressure found by using the available thrust. The stall velocity can be found using C_Lmax found in earlier simulations.
