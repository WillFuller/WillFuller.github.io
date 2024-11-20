---
title: "Designing A Probe Head For Extreme Environments"
date: 2024-11-19
permalink: /posts/2024/11/design-extreme-env/
tags:
  - PhD
  - Design
  - Turbulence Probe
  - UKAEA
  - Warwick
---

Over the course of my PhD, I have had the opportunity to spend the past few years working closely with the team at MAST-U. MAST-U is a spherical tokamak based at the [UKAEA](https://ccfe.ukaea.uk/programmes/mast-upgrade/) Culham campus in Oxford. The machine is home to one of the most intense man-made environments. Maximum core temperatures of around 3 keV (34 million °C), an ultra-high vacuum (~10<sup>-6</sup> mbar), electrically conductive plasma with high currents up to 1 MA, and neutron rates on the order of ~10<sup>14</sup> high-energy neutrons per discharge. How do you design a probe to survive these conditions?

![MAST-U](/images/MAST-U_picture_updated_smaller.jpg){:width="249px" height="223px"}

Firstly, minimising the time the probe spends in contact with the plasma helps survivability. The probe is mounted on a compressed air driven reciprocating arm capable of moving the probe up to 9 cm at a speed of 4.5 ms<sup>-1</sup> (10 mph).

![RP system](/images/RP_CAD.png){:width="249px" height="223px"}

Secondly, careful design considerations bearing in mind the environment it will regularly operate in. A good summary can be found on my poster [here](/files/graphical_abstract_design_probe.pdf).

The main factor is the materials used for the probe. The probe is protected with a ceramic shell made from Boron Nitride. BN has a layered hexagonal structure similar to graphene, and shares similar material properties to graphene, notably, high temperature tolerance (~1500 °C), low thermal expansion, and good vacuum compatibility. Unlike graphene, it is  not electrically conductive, perfect for an electrical probe inside a plasma. Another benefit due to the layered structure of BN, is if the probe spends too long in the plasma, the top layers burn off, leaving the rest of the shell intact.

![Turbulence Probe Head](/images/turb-probe-size-photo.jpg){:width="249px" height="223px"}

Maintainability is key. These probes are custom build in-house at UKAEA (by yours truly) and this means they may not always work properly, so the ability to easily repair and upgrade the probe is vital. What better way to understand the maintenance problem then to get hands on with existing probe. One of the most frustrating things I learned was that the graphite probe tips are super fragile (the worst was after hours of wrestling the shell on, the wires twisted the tip and it snapped just as I thought I finished 😒). So we designed several ways to reduce the stress on the tips. Thicker tips for a start (apart from the top), preventing the wires from twisting the internal stack, finally, reducing the number of unique sized tips so we could order more spares.

![Mach Probe Head](/images/mach_probe_size_photo.jpg){:width="249px" height="223px"}

One thing we didn’t anticipate, to make sure the probe is vacuum compatible, it needs to have all of the moisture baked out of it, so the finished probe head was put into a vacuum oven and heated to 200 °C for 6 hours. Disaster strikes! The internal PEEK components expanded by 0.7 mm, splitting the brittle ceramic shell in half! Version 2 now has smaller diameter internal components leaving a gap of 1.5 mm, plenty of room to expand… this probe is aiming to be installed ready for experiments next year.

![Split shell cap](/images/turb-probe-shell-split.jpg){:width="249px" height="223px"}

Why did we build this? To explore the outer edge of the plasma to better understand the intermittent plasma bursts (called filaments) in the edge, bringing heat and particles from the core onto the walls of the machine. This reduces performance, and can cause damage to the machine over time. You can find more detail on the layout of the probe tips for the Turbulence Probe Head we build [here](/portfolio/turb-probe-array/).

*[UKAEA]: United Kingdom Atomic Energy Authority
*[MAST-U]: Mega Ampere Spherical Tokamak - Upgrade
*[RP]: Reciprocating Probe
*[BN]: Boron Nitride
*[PEEK]: PolyEther Ether Keytone
