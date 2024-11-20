---
title: "Turbulence Probe Head Arrays"
excerpt: "The Turbulence Probe Head contains 15 probes laid out in a variety of multi-functional arrays.<br/><img src='/images/shell_cap_schematic_colour_coords.png' alt='Colour-coded schematic showing the layout of the Turbulence Probe arrays.' width='249' height='223'>"
collection: portfolio
---

![turb probe](/images/shell_cap_schematic_colour_coords.png "Colour-coded schematic showing the layout of the Turbulence Probe arrays."){:id="fig_colour_schematic"}

The Langmuir Probe arrays of the Turbulence Probe Head are made up of of 13 Langmuir Probes, and 2 Ball-Pen Probes. These probes are laid out on the probe head in a variety of multi-functional arrays. Figure [1](#fig_colour_schematic) shows the shell cap with the probe arrays highlighted. The features included in the design are:

* log-spaced LP
* BPP
* 5-pin BTLP
* velocity array
* Mach probes
* internal noise pickup probe
* 3-axis magnetics coil

### Log-spaced Array {#subsec_log_space}

The log-spaced LP array, shown in blue in figure [1](#fig_colour_schematic), is 4 probes spaced logarithmically across the centre of the probe head in the poloidal direction, to perform cross-correlation calculations on a broad range of length scales. This is useful for searching for turbulent frequencies across a range of probe spacings across \\(k_\theta\\) space and phase space simultaneously [^1] [^2].

### Ball-Pen Probe Array {#subsec_bpp_array}

The Ball-pen Probes are capable of measuring plasma potential \\(\Phi\\), and are positioned close to a cluster of other probes collecting \\(V_\mathrm{Float}\\) to provide an estimate of \\(T_\mathrm{e}\\). Recent work by _Adamek et al_ [^3] shows that with sufficiently high frequency sweeping (\\(\geq\\) 500 kHz), the BPP can directly measure ion current. The BPP is discussed in further detail in this post [here](/portfolio/lp-description/). The BPP are coloured green in figure [1](#fig_colour_schematic), along with the floating pins nearby that are also part of the 5-pin BTLP.

### 5-pin Balanced Array {#subsec_btlp_array}

The 5-pin BTLP array of 5 LP near the centre of the probe head, is coloured pink in figure [1](#fig_colour_schematic). Further details are discussed [here](/portfolio/lp-description/). This array can be used as a TLP or as a BTLP array, measuring simultaneously \\(T_\mathrm{e}\\) and \\(n_\mathrm{e}\\). To avoid shadowing the central pin by the surrounding pins, the central pin was raised 1.5 mm, peaking above the other pins.

### Velocity Array {#subsec_velarray}

The linearly spaced velocity array (shown in yellow in figure [1](#fig_colour_schematic)), described in this [post](/portfolio/lp-description/), was designed primarily to measure the statistics of radial velocities of filaments (plasma bursts at the edge region). It is also capable of estimating the radial width, poloidal velocity, and amplitude distributions.

### Mach Array {#subsec_mach_array}

Two probes offset from the top of the probe by allows the main body to act as a barrier, measuring the parallel Mach number for plasma flow (see [here](/portfolio/lp-description/) for details), shown in red in figure [1](#fig_colour_schematic).

### Internal Noise Pick-up Probe {#subsec_noise}

A probe isolated from the plasma was included to act as a noise pickup. It measures systematic noise from the RP system, making data processing simpler by subtracting this signal from the other probes. The noise in the system includes induction from rapidly moving through strong magnetic fields, and losses from ~25 m long cables from the blockhouse where MAST-U is located, to the South Annex where the RP data processing cabinet is located.

### 3-Axis Magnetic Field Pickup Coil {#subsec_mag_pickup}

Finally, a 3-axis magnetic field pickup coil to collect information on the radial, toroidal and poloidal magnetic fields as the probe moves into the plasma was included, The coils consist of 36 AWG enamelled copper wire with 48 turns. This coil can be used to help calculate quantities such as the radial turbulent flux \\(\Gamma_r^{\mathrm{turb}}\\), and during commissioning to make sure the probe head is correctly orientated to the magnetic field for the probe arrays.

*[AWG]: American wire gauge
*[BN]: boron nitride
*[BPP]: Ball-Pen probe
*[BTLP]: balanced triple Langmuir probe
*[LP]: Langmuir probe
*[MAST-U]: Mega Ampere Spherical Tokamak - Upgrade
*[RP]: reciprocating probe
*[TLP]: triple Langmuir probe

[^1]: Beall, J. M., Kim, Y. C. & Powers, E. J. Estimation of wavenumber and frequency spectra using fixed probe pairs. en. _Journal of Applied Physics_ **53**, 3933–3940. <doi:10.1063/1.331279>. (2022) (June 1982).
[^2]: Grenfell, G. _et al._ The multi-faced nature of the quasicoherent mode in EDA H-mode. en. _Nuclear Fusion_ **64.** Publisher: IOP Publishing, 104002. <doi:10.1088/1741-4326/ad751b>. (2024) (Sept. 2024).
[^3]: Adamek, J. _et al._ Ion temperature measurements in the tokamak scrape-off layer with high temporal resolution. en. _Nuclear Fusion_ **61**, 036023. <doi:10.1088/1741-4326/abd41d>. (2023) (Mar. 2021).
