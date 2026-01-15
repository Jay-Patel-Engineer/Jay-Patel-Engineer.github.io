---
layout: post
title: Bipropellant Liquid Rocket Engine
description: The development of a liquid rocket engine utilizing kerosene and nitrous oxide as the fuel and oxidizer. The development included the design, manufacturing, and testing of the Thrust Chamber, Thrust Stand, and Plumbing System.
skills: 
- Fluid Flow
- Thermodynamics
- Structural Analysis
- Systems and Control
- Manufacturing
- CEA Analysis
- Data Collection and Analysis
main-image: /LRE.png 
---

---
## Initial Project Conditions
Beyond the development of a liquid rocket engine, three constraints were also included in the initial request for the project. These constraints include a target performance metric, propellant storage, and a budget. The requested performance metric is defined by a target thrust of 300 Newtons. The propellant sourcing constraint outlines the use of propellants that can be stored and used without the need for cryogenics. Finally, the initial proposed budget is $1,000. All parts are also manufactured with aluminum for ease of manufacturing and cost unless stated otherwise.
## Manufacturing
The manufacturing process primarily utilized a lathe; however, some parts were modified using a vertical mill. Before beginning manufacturing, a tolerance needed to be decided to improve machining feasibility. Due to the simple nature of most of the parts, tolerancing was simply determined using ISO 2768 as a guide. While the different parts need to be fitted together, they do not need to be perfect. The most crucial fit of the complete assembly is the seal created between the injector plate and the combustion chamber. However, this seal was later reinforced by a set of O-rings. The second most important tolerances are the ones that govern the diameter of the orifices located on the injector plate. These orifices control the flow rate of propellants and are sized to achieve the necessary flow rate for efficient combustion. A cylindricity tolerance was applied to these orifices.
{% include image-gallery.html images="nozzle_holder.png, nozzle_insert.png" height="400"%}
<span style="font-size: 20px">Nozzle Holder and Nozzle Insert</span>
{% include image-gallery.html images="assembled_chamber.png" height="400"%}
<span style="font-size: 20px">Assembled Thrust Chamber</span>
{% include image-gallery.html images="machined_injector.png" height="400"%}
<span style="font-size: 20px">Pintle Injector</span>
{% include image-gallery.html images="assembled_stand.png" height="400"%}
<span style="font-size: 20px">Assembled Thrust Stand Without Mounted Plumbing System or Thrust Chamber</span>
## Testing
The injector plate, thrust chamber, and solenoid valves underwent an additional round of testing prior to the hot fire to ensure proper functionality. A cold flow testing procedure was used to determine the efficiency of the injector plate. This test consisted of pumping water through the injection plate to visualize the impingement of the two propellant streams. The valve timings can also be experimentally determined through cold flow testing as well. 
{% include youtube-video.html id="IlmzLuZ_n98" autoplay= "false"%}
<span style="font-size: 20px">Oxidizer Cold Flow Testing</span>
{% include youtube-video.html id="0Mt1T-wTBKM" autoplay= "false"%}
<span style="font-size: 20px">Fuel Cold Flow Testing</span>
The thrust chamber has been designed in order to withstand a pressure of 300 psi. To ensure its structural integrity as well as its seal, hydrostatic testing was performed. This test consisted of plugging all exit points on the thrust chamber and then pumping water via a hand pump. The final results of this test show that the thrust chamber can sustain a pressure of 500 psi for at least two minutes, which is more than enough for the planned five-second burn. 
{% include youtube-video.html id="54BqEur4c8U" autoplay= "false"%}
<span style="font-size: 20px">Thrust Chamber Hydrostatic Testing</span>
The solenoid valves were tested for functionality, confirmation of the rated pressure, and correct actuation timings. Once these three components were tested, trial runs of the hot fire began.
{% include youtube-video.html id="tlTq_UFrETE" autoplay= "false"%}
<span style="font-size: 20px">Test Fire 1</span>
{% include youtube-video.html id="xCFsjYxbUxk" autoplay= "false"%}
<span style="font-size: 20px">Test Fire 2</span>
---
The following sections contain in-depth analysis and demonstrate the design process of major components.
## CEA Analysis
Of the propellants readily available without the need for cryogenic storage, kerosene and nitrous oxide best fit this description. To determine the several other parameters needed to begin the design of the thrust chamber, NASA's CEARUN software was utilized. This software allows for quick calculations of several constants related to the gas produced after combustion, such as its temperature, specific heat, and specific impulse. By varying the initial chamber pressure, the relationship between specific impulse, oxidizer-to-fuel ratio, and chamber temperature can be analyzed. While the ideal design would use an oxidizer-to-fuel ratio of about 7, the temperature generated by the combustion would be too high. Thus, a ratio of 2.3 was selected.
{% include image-gallery.html images="CEA_Analysis.png" height="400"%}
<span style="font-size: 20px">Data Collected by CEARUN</span>

| Parameter | Chamber | Nozzle Throat | Nozzle Exit | Unit |
|----------|----------|----------|----------|----------|
| Pressure | 20.700 | 11.389 | 1.000 | Bar |
| Temperature | 1691.45 | 1492.14 | 1024.22 | K |
| Cp | 2.1608 | 2.2369 | 6.7011 | N/A |
| Specific Heat | 1.2702 | 1.2733 | 1.1555 | N/A |
| Mach Number | N/A | 1 | 2.602 | N/A |
| Specific Impulse | N/A | 92.8 | 185.9 | seconds |
| Specific Impulse (Vacuum) | N/A | 165.6 | 209.6 | seconds |
| C* | N/A | 1298.0 | 1298.0 | m/s |
| A/A* | N/A | 1 | 3.5912 | N/A |

## Thrust Chamber
The thrust chamber is an assembly of the combustion chamber, nozzle, and injector plate. The thrust chamber houses all the components required to ensure efficient propellant injection, propellant combustion, and combustion exhaust. Each component's design process and analysis is described in detail in the following sections.
{% include image-gallery.html images="thrust_chamber.png" height="400"%}
<span style="font-size: 20px">Internal View of Assembled Thrust Chamber</span>
### Combustion Chamber
The combustion chamber houses the main brunt of the combustion. For that reason, it must be built to withstand any and all thermodynamic and stress forces. From the prior CEA analysis, the required specifications for the combustion chamber can be found. In order to increase the ease of manufacturing, several factors were also considered. These factors include the relationship between the contraction ratio of the combustion chamber and expansion ratio of the nozzle as well as the critical length. By ensuring the contraction ratio is larger than the expansion ratio, the ease of manufacturing increases substantially with little to no performance impact on the final product.
{% include image-gallery.html images="combustion_chamber.png" height="400"%}
<span style="font-size: 20px">CAD Design of Combustion Chamber</span>
### Injector Plate
The injector plate is undoubtedly the most important component of the thrust chamber. It is responsible for delivering both propellants at their required flow rates as well as ensuring optimal mixing prior to combustion. Of the several designs and methods that exist for propellant injection, the final selection was between an impingement injector and a pintle injector. The main difference between these two is the delivery method of the propellants; the former uses angled paths to impinge both propellant streams, and the latter uses a radial injection method. The pintle injector is far more efficient and easier to manufacture due to its radial nature, thus making it the final selection. To minimize risks of combustion backflow, dead space within the pintle injector was reduced as much as possible while still maintaining manufacturability.
{% include image-gallery.html images="pintle_injector1.png, pintle_injector2.png" height="400"%}
<span style="font-size: 20px">Cross-section of Pintle Injector</span>
### Nozzle
The nozzle is responsible for compressing the combustion gas before allowing for rapid expansion back to atmospheric pressures. This creates a massive increase in exit flow speed, which is essential to hit the target thrust. This type of nozzle is referred to as a converging-diverging nozzle. Due to the sudden compression of the combustion gasses, temperature levels can skyrocket. After experimenting with different materials, the final design utilized an aluminum nozzle carrier and a copper throat insert. A copper throat insert was selected for two main reasons: its resistance to erosion due to the combustion gasses and its high heat transfer coefficient. The resistance to erosion allows for multiple test fires without having to change the nozzle insert frequently, while the high heat transfer coefficient allows the nozzle insert to dissipate heat flux to the aluminum nozzle carrier as efficiently as possible. The final consideration that must be made for the nozzle is its expansion ratio. The most efficient final product will ensure that the exit exhaust is perfectly expanded back to the atmospheric pressure.
{% include image-gallery.html images="nozzle.png" height="400"%}
<span style="font-size: 20px">Nozzle Carrier and Nozzle Throat Insert</span>
## Thermal and Stress Analysis
To ensure that the thrust chamber will be able to withstand the extreme thermal forces and stress forces, a simulation was conducted using ANSYS Mechanical. The results of the simulation show that the peak combustion temperature and peak stress are well below the respective deformation limits of the aluminum thrust chamber. The stress simulation is later verified through hydrostatic testing after manufacturing. 
{% include image-gallery.html images="thermalsim.png, stresssim.png" height="400"%}
<span style="font-size: 20px">Simulation Results via ANSYS</span>
## Thrust Stand
The main design philosophy behind the thrust stand is that it should be able to withstand and effectively distribute all forces applied to it over the course of a test fire. These forces include the weight of all components attached to the thrust stand as well as any additional forces due to generated thrust. A secondary, but equally as important, consideration for the thrust stand design is that it should separate the propellants to minimize the risk of an uncontrolled combustion. Finally, the thrust stand should also be able to house any and all monitoring equipment used for the purposes of data collection.
{% include image-gallery.html images="thrust_stand.png" height="400"%}
<span style="font-size: 20px">Assembled Thrust Stand</span>
## Plumbing System
Alongside the injector plate, the plumbing system is also one of the most vital systems. Due to the volatility of the propellants, the plumbing system should be designed in a manner that ensures the propellant never mixes before crossing the injector plate. The lines should also always be purged with an inert gas to ensure no propellant is left in the system before and after a test fire. This can be achieved easily by having separate plumbing systems for each propellant. However, this method results in a larger manufacturing cost due to the need to purge both systems separately. In order to reduce manufacturing cost while maintaining product efficiency, a single plumbing system was designed. Before designing the plumbing system, some considerations concerning the propellant delivery method must be made. In the case of nitrous oxide, due to its high vapor pressure, nitrous oxide is a self-pressurizing gas. This allows nitrous oxide to travel to the injector plate by simply opening the valve. Kerosene, however, does not follow this logic. The typical way to deliver kerosene from its tank to the injector plate is via a pump. However, pumps can be costly and complicated. Another method, and the method that was selected, is to use a different pressurized gas to propel the kerosene through the plumbing system. This gas would need to be inert so that it does not react with the kerosene while pressurizing. The best gas for this case would be compressed nitrogen. Nitrogen would also double as the purging gas.
{% include image-gallery.html images="P&ID.png" height="400"%}
<span style="font-size: 20px">Final P&ID Including all Redundancy Valves</span>
{% include image-gallery.html images="PlumbingCAD.png" height="400"%}
<span style="font-size: 20px">Plumbing System Designed in CAD</span>
