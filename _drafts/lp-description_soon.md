---
title: "The Physics behind Langmuir Probes"
excerpt: "Langmuir Probes are abundant in plasma science as they provide relatively straightforward, direct measurements of key plasma parameters"
collection: portfolio
---

## Langmuir Probes {#sec_Langmuir-Probes}

A Langmuir Probe in the most basic sense, is an electrode that interacts with a plasma and measures a voltage or current. LPs are abundant in plasma science as they provide relatively straightforward, direct measurements of key plasma parameters. However, they are not free from drawbacks or assumptions in operation. They take their name after Irving Langmuir who published an article in 1926 \cite{mott-smith_theory_1926} along with H. M. Mott-Smith entitled ``The Theory of Collectors in Gaseous Discharges'' in which they describe:
\begin{quotation}
    ``the determination of the complete volt-ampere characteristic of a small auxiliary electrode or collector of standard shape placed in the path of the discharge, and in the interpretation of this characteristic according to a new theory.''
\end{quotation}

<figure>
    <img id="fig_IV_curve" src="figures//diagnostics/IV_curve.png" alt="_IV_ Curve for a probe." width="" height="">
    <figcaption>A typical _IV_ curve for a Langmuir Probe showing the ion saturation current, floating potential, the electron saturation current, the plasma potential, and the electron temperature.</figcaption>
</figure>

Langmuir and Mott-Smith measured the ion saturation current of their plasma by applying a voltage bias, with respect to the plasma, to the probe that created a negative potential sheath. The sheath repelled all electrons, attracting ions until it was fully saturated and would not attract ions any further. The ion saturation current is given by \cite{boedo_transport_2001,hutchinson_principles_2002}:

$$
    I_\mathrm{Sat} = \frac{1}{2} A e n c_\mathrm{s} \propto n \sqrt{T_\mathrm{i} + T_\mathrm{e}} \label{eq:IsatFull}
$$
When $A$, the area of the probe, and the sound speed $c_\mathrm{s}$ of ions and electrons is known, the density can be calculated. A potential can be established in the probe such that a sufficiently negative voltage applied across the probe creates a negative sheath around the probe, repelling electrons and attracting the ions from the plasma, this potential can be used to measure the ion saturation current from which it is possible to calculate ion density and temperature.

LP typically operate in three distinct modes, giving access to different properties of the plasma, they are:

    * Floating Potential mode, in which no external bias is applied, the probe voltage is allowed to float with reference to the plasma potential, see [subsec_float](#subsec_float) for details.
    * Bias Potential mode, where a bias dc voltage is applied to the probe, typically probes are biased negatively with respect to the plasma potential, to measure the ion saturation current. [subsec_bias](#subsec_bias) has further details.
    * Swept voltage mode. In this operational mode the voltage applied to the probe is swept, typically on the order of 10s of kHz. Usually, the voltage range swept goes from slightly positive, to negative, in order to capture _IV_ characteristics of the plasma. See [subsec_swept](#subsec_swept).

### Floating Probes {#subsec_float}

The simplest operation for a probe is to allow the probe's voltage to float with respect to the varying plasma potential. The floating potential is where $I^-$ and $I^+$ cancel to give no net current. This potential, $V_\mathrm{Float}$, lies somewhere between the electric potential of the sheath and the plasma potential $\Phi_{\mathrm{Plasma}}$, $V_\mathrm{Float}$ is negative with respect to $\Phi_{\mathrm{Plasma}}$. The floating potential is given as \cite{monk_langmuir_1996}:
$$
    V_\mathrm{Float} = V_{\mathrm{plasma}} - \frac{T_\mathrm{e}}{2 e} \ln{\left[2 \pi \frac{m_\mathrm{e}}{m_\mathrm{i}} \left(1 + \frac{T_\mathrm{i}}{T_\mathrm{e}}\right)\right]} \label{eq:vf}
$$
Note the temperature used in these equations are in units of \acf{eV}, to convert temperatures between Kelvin (K) and eV the equation $T_\mathrm{K} = e T_\mathrm{eV} / k_\mathrm{B}$ is used, where $e$ is the electron elementary charge ($1.6 \times 10^{-19}$ C), and $k_\mathrm{B}$ is the Boltzmann constant ($1.38 \times 10^{-23}$ JK<sup>-1</sup>). Using the energy equipartition assumption, such that $T_\mathrm{i} \approx T_\mathrm{e}$, and for a deuterium plasma equation \eqref{eq:vf} becomes:
$$
    V_\mathrm{Float} \approx V_{\mathrm{plasma}} - 3 \frac{T_\mathrm{e}}{e} \label{eq:vfloat}
$$

 % this equation tells us that the floating potential of a probe can be a proxy to the plasma potential and the electron temperature. from this, assuming the temperature can be measured from another diagnostic (Thomson) we can find the radial electric field by correcting the floating potential from the temperature, a proxy of the plasma potential, subtracted from itself in time or space would give a good approximation of the electric field.

### Bias Probes {#subsec_bias}

Another operational mode for LP is to apply a constant voltage to bias the probe in the plasma. If the applied voltage is increased further, the probe will reach a stable current draw, called the saturation current $I_\mathrm{Sat}$. If the applied voltage is negative relative to $\Phi_{\mathrm{Plasma}}$ the probe will repel electrons, and collect net ions. This current is called the ion saturation current, $I^+_{\mathrm{Sat}}$.

The ion saturation current is defined as \cite{monk_langmuir_1996}:
$$
    I^+_{\mathrm{Sat}} = j^+_{\mathrm{Sat}} A_{\mathrm{pr}} = \frac{1}{2} n_\mathrm{0} e c_\mathrm{s} A_{\mathrm{pr}} \label{eq:isat}
$$
Where $c_\mathrm{s}$ is the ion sound speed, $j^+_{\mathrm{Sat}}$ is the ion current density, $A_{\mathrm{pr}}$ is the collection area of the probe, and $n_\mathrm{0}$ is the unperturbed plasma density far away from the probe. As shown in equation \eqref{eq:isat}, the ion saturation current is proportional to the density and is often used as a proxy for density in plasma measurements.

An applied voltage that is positive, relative to $V_\mathrm{Float}$ will collect net electrons. Assuming a Maxwellian distribution of electron velocities and neglecting secondary electron effects the current drawn is given by:
$$
    I^- = \frac{1}{4} n_\mathrm{0} e \bar{c_\mathrm{e}} A_{\mathrm{pr}} \exp{\left[ \frac{\left(V_{\mathrm{app}} - V_{\mathrm{plasma}} \right)}{T_\mathrm{e}} \right]} \label{eq:ecurrent}
$$
Where $\bar{c_\mathrm{e}}$ is the random thermal electron flux.
A sufficiently positive voltage will saturate at the electron saturation current $I^-_{\mathrm{Sat}}$.
$$
    I^-_{\mathrm{Sat}} = \frac{1}{4} n_\mathrm{0} e \bar{c_\mathrm{e}} A_{\mathrm{pr}} \label{eq:esat}
$$

Experimentally $I^-_{\mathrm{Sat}}$ is typically not measured with LP as it usually draws too much particle flux from the more mobile electrons, creating a large spike in current, and a significant increase in power applied to the probe, potentially damaging the probe and the power supply. Additionally, $I^-_{\mathrm{Sat}}$ can significantly perturb the plasma. For these reasons we will consider only the ion saturation current $I^+_{\mathrm{Sat}}$.

### Swept Probes {#subsec_swept}

A typical operational mode for LP is to sweep the bias voltage across the probe to acquire an I-V characteristic. This I-V curve contains the information needed for calculating the $I^+_{\mathrm{Sat}}$, $V_\mathrm{Float}$, and $T_\mathrm{e}$. This voltage sweep can be repeated at a high frequency (kHz) to enable sufficient LP measurements with an acceptable time resolution to be included on the walls of many plasma devices.

Swept LP _IV_ curves are usually fit using a 4-parameter model \cite{gunn_flushmounted_1995,tsui_accounting_2018}.

$$
    I(V) =
    \begin{cases}
        I^+_{\mathrm{Sat}} \left[\exp{\left(\frac{V-V_\mathrm{Float}}{T_\mathrm{e}}\right)} - 1 \right] \quad \text{if } V_\mathrm{Float} \le V < V_{\mathrm{plasma}} \\
        \\
        I^+_{\mathrm{Sat}} \left[\exp{\left(\frac{V-V_\mathrm{Float}}{T_\mathrm{e}}\right)} - 1 \right] - \alpha(V_\mathrm{Float} - V) \quad \text{if } V < V_\mathrm{Float}
    \end{cases} \label{eq:4param}
$$

Here, the term $\alpha\left(V_\mathrm{Float} - V\right)$ accounts for the non-saturation of the net ion current region due to sheath expansion as the probe is swept more negative than the floating potential \cite{gunn_flushmounted_1995,tsui_accounting_2018,ryan_overview_2023}. For the 4-parameter fit, $\alpha$ is treated as the ion current per volt due to the sheath expansion, $\alpha = \frac{\Delta I}{\Delta V}$, and the probe voltage must satisfy $V < V_\mathrm{Plasma}$ where $V_\mathrm{Plasma}$ is the electric potential of the bulk plasma \cite{adamek_ion_2021,tsui_accounting_2018}. From [fig_IV_curve](#fig_IV_curve), the first term of equation \eqref{eq:4param} fits to the exponential portion of the _IV_ curve between $V_\mathrm{Float}$ and $V_\mathrm{Plasma}$, and the second term is used to fit to the portion $< V_\mathrm{Float}$. The 4 parameters fitted to the data are $I^+_\mathrm{Sat}, \, V_\mathrm{Float}, \, T_\mathrm{e}, \text{ and } \alpha$. $T_\mathrm{e}$ can be measured with other diagnostics, or estimated from the gradient of the _IV_ curve as shown in [fig_IV_curve](#fig_IV_curve), with $I^+_\mathrm{Sat} \text{ and } V_\mathrm{Float}$ measured directly, and $\alpha$ treated as a curve fitting parameter.

% swept profiles are great at collecting a lot of data for the device and can be useful in looking at average profiles of the plasma. because they are swept they are not great at looking for specific times and time based analyses. but provide excellent averaged data so looking at what was happening in the plasma is a great generalisation.

### Mach Probes {#subsec_machtheory}

Mach probes are designed to study plasma flows by placing a barrier between probes in order to separate upstream and downstream flows. The most basic of these is to construct probes with a barrier between them to measure the parallel flow of the plasma see figure [fig_mach-cartoon](#fig_mach-cartoon). In a strong magnetic field such as found in tokamaks, where $\rho_\mathrm{i} \ll a$ ($a$ is the probe radius), the ion collection is diffusive even when the parallel flow is dominated by inertial effects \cite{hutchinson_fluid_1987,hutchinson_principles_2002}.

<figure>
    <img id="fig_mach-cartoon" src="" alt="A simple mach probe measuring parallel plasma flows." width="" height="">
    <figcaption>A simple mach probe measuring parallel plasma flows. Reproduced from \cite{chung_mach_2012}</figcaption>
</figure>

For two probes with a barrier between them (a Mach probe, see [fig_mach-cartoon](#fig_mach-cartoon)), the ratio of upstream and downstream ion currents is equal to $\exp{(M_\infty / M_\mathrm{c})}$, with $M_\mathrm{c} = 0.45$ as the calibration Mach number.
For the parallel Mach number, we assume $M_\infty \approx M_\parallel$ which gives $M_\parallel$ as

$$
    M_\parallel = 0.45 \ln{\frac{J_\mathrm{upstream}}{J_\mathrm{downstream}}} = \frac{v_\parallel}{c_{\mathrm{s}}} \label{eq:mpara}
$$

### Ball-Pen Probes {#subsec_BallPenProbes}

BPP are a novel version of an LP originally designed to directly measure the plasma potential $\Phi$, by balancing the incoming electron and ion saturation currents to 1, removing the temperature contribution from equation \eqref{eq:vfloat} \cite{adamek_direct_2014,adamek_fast_2017,adamek_profile_2016,murphy-sugrue_numerical_2017,murphy-sugrue_improved_2017,walkden_profile_2015}. This is achieved by retracting the probe collection surface below the surrounding shielding, insulating the probe from most of the higher mobility electrons as they have a smaller gyroradius. Some electrons hit the insulated wall around the probe and bias it negatively, attracting the less mobile ions, with a larger gyroradius to the probe. Figure [fig_bpp-schematic](#fig_bpp-schematic) shows a cartoon of a BPP cross section, highlighting this behaviour. This reliance on the probe geometry is not the only mechanism at work here, as explored by \citet{murphy-sugrue_improved_2017}, where 3D PIC simulations were performed, revealing that the opposing gyro-orbits of the ions an electrons create an electric field across the opening of the BPP. This induces a perpendicular $\mathbf{E} \times \mathbf{B}$ drift down the insulator towards the collector, a sheath is formed on the walls of the tunnel, and this reflects the electrons from side to side until the $\mathbf{E} \times \mathbf{B}$ drift takes them to the collector. Ions, with the larger gyro-radius, tend to impact the collector directly. Whilst the depth of the BPP retraction is shown to not affect the operation of the device, (provided it is sufficiently large, $h > \rho_\mathrm{e}$) the simulations suggest the diameter of the probe may affect the ion collection, with a wider diameter allowing more ions to interact with the collector instead of the tunnel walls.

BPP are typically operated in the floating regime. This allows the probe to measure a good approximation to the plasma potential, as seen in the following equation \cite{adamek_direct_2014,walkden_profile_2015,adamek_profile_2016,adamek_transport_2020}.
$$
    V_\mathrm{Float} = V_{\mathrm{plasma}} - \alpha_\mathrm{BPP} T_\mathrm{e}. \label{eq:bppfloat}
$$
Where $\alpha_\mathrm{BPP}$ is given by:

$$
    \alpha_\mathrm{BPP} = \ln{\left[ \frac{I_\mathrm{Sat}^-}{I_\mathrm{Sat}^+} \right]} = -0.5 \ln{\left[2 \pi \frac{m_\mathrm{e}}{m_\mathrm{i}} \left( 1 + \frac{T_\mathrm{i}}{T_\mathrm{e}}\right)\right]}. \label{eq:bpp_alpha}
$$
From equation \eqref{eq:bppfloat}, a BPP can directly measure $V_{\mathrm{plasma}}$ by balancing $I_\mathrm{Sat}^-/I_\mathrm{Sat}^+$ to unity, eliminating the $T_\mathrm{e}$ component from the equation. 

Recent studies further exploiting BPP have shown fast sweeping a voltage, typically on the order of 10kHz, across a BPP allows measurement of $T_\mathrm{i}$ \cite{adamek_ion_2021,cipciar_ion_2021}. This is done by sweeping the probe voltage into the electron saturation branch of the _IV_ curve ([fig_IV_curve](#fig_IV_curve)). The data is then fitted using a 4-parameter fitting model, where $K$ is $\frac{\Delta I}{\Delta V} = \alpha = K$ as in equation \eqref{eq:4param}.

$$
    I(V) = I_\mathrm{Sat}^- [1 + K(V + V_\mathrm{Plasma})] - I_\mathrm{Sat}^+ \exp{\left( \frac{V_\mathrm{Plasma} - V}{T_\mathrm{i}} \right)}. \label{eq:BPP_4param_full}
$$

Using equation \eqref{eq:bpp_alpha} we obtain:
$$
    I_\mathrm{Sat}^- = I_\mathrm{Sat}^+ \exp{(\alpha_\mathrm{BPP})}. \label{eq:BPP_Isats}
$$

equation \eqref{eq:BPP_4param_full} becomes:
$$
    I(V) = I_\mathrm{Sat}^+ \left[ \exp{(\alpha_\mathrm{BPP})}[1 + K(V - V_\mathrm{Plasma})] - \exp{\left( \frac{V_\mathrm{Plasma} - V}{T_\mathrm{i}} \right)}\right] \label{eq:BPP_4param_simplified}
$$

equation \eqref{eq:BPP_4param_simplified} is fitted to data in the range $V > V_\mathrm{Plasma}$, due to this model only being valid for the electron saturation branch, two fits must be performed, the first fit to determine the plasma potential $V_\mathrm{Plasma}$, and the second fit for all the values only above the plasma potential. Checks are also performed to ensure $V \geq 3 T_\mathrm{i}$, where the linear region of the _IV_ curve dominates. Otherwise a reduced fit is performed using equation \eqref{eq:BPP_4param_simplified} where $K = 0$ to refit the _IV_ characteristic without the linear contribution \cite{adamek_ion_2021}.

<figure>
    <img id="fig_bpp-schematic" src="figures/diagnostics/bpp-schematic.png" alt="Cartoon showing the principle of the BPP operation." width="" height="">
    <figcaption>Cartoon showing the principle of the BPP operation, reproduced from \cite{walkden_profile_2015}.</figcaption>
</figure>

## Multi-Probe Arrangements {#sec_Multi-Probe-Arrangements}

It can be advantageous to group probes into multi-probe arrangements, for measuring different properties of the plasma, and to get multi-point measurements that give access to additional plasma parameters, such as advection velocity of density structures (filaments, blobs). This extra dimensionality is possible as the probes are a known fixed separation from each other, so for example as a blob structure passes one probe then reaches the next, the speed of the blob and the width can be calculated. The pin alignment would need to be accounted for, such that there was no shadowing each other whilst maintaining alignment with the direction of filament motion.

### Double Probes {#subsec_double}

Double probes are connected together as shown in figure [fig_cir_DP](#fig_cir_DP)} and a bias voltage is swept across them. Due to this configuration the probes are limited to measuring $I^+_{\mathrm{Sat}}$ and $-I^+_{\mathrm{Sat}}$, this makes data collection and interpretation a simpler process compared to a swept single LP. An additional advantage is the probe potentials are relative to each other, so the probes do not perturb each other. However these factors are traded off with less spatial resolution and the assumption of sampling the same plasma despite the probe separation. To ensure collection of $I^+_{\mathrm{Sat}}$, the sweeping voltage $V_{\mathrm{bias}}$ range should be sufficiently broad. One consideration that must be taken into account when operating this array, is to ensure that the probes are sufficiently far apart from each other to ensure they are on separate field-lines and not shadowing each other within each other's probe sheath.

By treating the double probe system as a single probe provided

$$
\begin{align}
    0 &= I_1 + I_2 \label{eq:I1I2} \\
    V_{\mathrm{Probe}} &= V_1 - V_2 \label{eq:vprobe}
\end{align}
$$
we arrive at the following expression for the _IV_ characteristic where $A_1$ and $A_2$ are the probe collection areas
$$
    I_1 = \frac{j_1 A_1 \left[ 1 - \exp{\left( e V_{\mathrm{Probe}} / T_{\mathrm{e}} \right)} \right]}{1 + \left( A_1 / A_2 \right) \exp{\left( e V_{\mathrm{Probe}} / T_{\mathrm{e}} \right)}} \label{eq:doubleIV}
$$

For the case of equal probe areas where $A_1 = A_2$, equation equation \eqref{eq:doubleIV} can then be expressed as
$$
    I_1 = j_1 A_1 \tanh{\left( \frac{e V_{\mathrm{Probe}}}{2 T_{\mathrm{e}}} \right)} \label{eq:doubleIV2}
$$

![DP circuit diagram](){:width="" height="" id="fig_cir_DP"}

### Triple Probes {#subsec_triple}

A TLP array is similar to the double probe, in that two probes are connected to either side of a power supply, but they are not swept, they are set with a constant bias potential between them. An additional probe in the near vicinity is introduced and left floating. This array measures three points on the _IV_ curve simultaneously, ($I\mathrm{Sat}^+, -I^+_\mathrm{Sat}, V_\mathrm{Float}$) thus allowing direct measurements of $T_\mathrm{e}, \text{ and } n_\mathrm{e}$. The bias probes operate such that one tip draws an ion sat current and the other a net electron current \cite{wesson_tokamaks_2004,hutchinson_principles_2002}. Using the electrostatic sheath theory:

$$
    I = \left( j_{\mathrm{i}} + j_{\mathrm{e}} \right) A = j_{\mathrm{i}} \left( 1 - \exp{\left[ \frac{e[V_1 - V_{\mathrm{Float}]}}{T_{\mathrm{e}}} \right]} \right) A \label{eq:probecurrent}
$$

Where $j_{\mathrm{k}}$ is current density for ion and electron species, $A$ is probe area, $V_\mathrm{Float}$ is floating potential and $T_{\mathrm{e}}$ is electron temperature. Given that $-I_\mathrm{Sat}^+ + I_\mathrm{Sat}^+ = 0$, and given the probe voltage supply is large, $e \left| V_{\mathrm{1}} - V_\mathrm{Float} \right| \gg T_{\mathrm{e}}$ the electron temperature can be directly measured in the following equation:

$$
    T_{\mathrm{e}} = \left( V_{\mathrm{2}} - V_\mathrm{Float} \right) / \ln{\left[ 1 + \frac{A_{\mathrm{1}}}{A_{\mathrm{2}}} \right]} \label{eq:probeTe}
$$

where $V_2$ is the electron collecting probe voltage and $A_{1/2}$ are the areas of the probes. It is also advantageous to mix multiple types of probes in one array in order to cross-validate measurements and achieve multiple measurements of the same plasma structure simultaneously. TLP are connected as shown in figure [fig_cir_TLP](#fig_cir_TLP).

![TLP circuit diagram](){:width="" height="" id="fig_cir_TLP"}

Care must be taken to avoid the three probes shadowing each other, and probes should be on separate field lines. Due to the direct measurements of plasma properties without the dependence on voltage sweeping, high temporally resolved measurements can be made, which are useful for turbulence measurements. However the same assumption as the double probes is applied where it is assumed the same plasma is being sampled despite the physical distance of the probes.

### 5-pin Balanced Triple Probe {#subsec_5pin}

In 1992, \citet{tsui_new_1992} proposed to add two additional probes to the triple probe array (\cref[subsec_triple](#subsec_triple)), since termed a 5-pin BTLP. One of the additional probes will be placed on the other side of the array and operate in floating mode. The second additional probe is connected into the negative side of the probe biasing circuit, such that these pins are arranged either side of the positive pin, connected as shown in figure [fig_cir_BTLP](#fig_cir_BTLP). The extra pins would allow calculations of a centred finite difference of the balanced pins, which is second order accurate. However, the pins will be spread across a larger area so it must be assumed that the probes are sampling the same plasma. With the new layout equation equation \eqref{eq:probeTe} becomes

$$
    T_{\mathrm{e}} = \left( V_4 - \left[ V_{\mathrm{Float \, 1}} + V_{\mathrm{Float \, 5}} \right] / 2 \right) / \ln{\left[ 1 + \frac{A_2 + A_3}{A_4} \right]} \label{eq:btlpTe}
$$

![BTLP circuit diagram](){:width="" height="" id="fig_cir_BTLP"}

## Magnetic Coils

Finally, a 3-axis pickup coil to collect information on the radial, toroidal and poloidal magnetic fields present as the probe reciprocates was included, The coils ($45.6 \times 22$ mm) consist of 36 AWG ($d = 0.125$ mm) enamelled copper wire with 48 turns. This coil can be used during commissioning to ensure the probe head is correctly orientated to the magnetic field to fully utilise the probe arrays. For a magnetic field varying in time the induced voltage is:
$$
    V = - \frac{\mathrm{d}}{\mathrm{d}t} \iint{\mathbf{B} \, \mathrm{d}\mathbf{S} \approx -A_\mathrm{eff} \dot{B}}. \label{eq:mag_coil}
$$
Where $\dot{B}$ is the magnetic field fluctuation, the effective coil area $A_\mathrm{eff} = N_\mathrm{turns} \, A_\mathrm{loop}$ is the number of coil turns multiplied by the area of a single loop. The magnetic field can be obtained by numerical integration.
$$
    B_i = \frac{1}{A_i} \int{\dot{B}_i \, \mathrm{d}t} \label{eq:b_coil}
$$
Where $A_i$ is the coil effective area orthogonal to the magnetic field component of index $i$. All three components of the magnetic field can be simultaneously be measured using orthogonal coils \cite{hutchinson_principles_2002,grenfell_electromagnetic_2019}.

*[AlN]: Aluminium Nitride
*[ASDEX]: Axial Symmetric Divertor Experiment
*[AUG]: ASDEX Upgrade
*[AWG]: American wire gauge
*[BES]: beam emission spectroscopy
*[BN]: boron nitride
*[BPP]: Ball-Pen probe
*[BTLP]: balanced triple Langmuir probe
*[CAD]: computer aided design
*[CCFE]: Culham Centre for Fusion Energy
*[CD]: conventional divertor
*[DBS]: Doppler backscattering system
*[EBW]: electron-Bernstein wave
*[ED]: extended divertor
*[ELM]: edge localised mode
*[ENDF]: evaluated nuclear data file
*[eV]: long=electron volt
*[GPI]: gas puff imaging
*[HFS]: high-field side
*[H-mode]: high confinement mode
*[IAEA]: International Atomic Energy Authority
*[ITER]: International Thermonuclear Experimental Reactor
*[JET]: Joint European Torus
*[JANIS]: Java-based nuclear data information system
*[LCFS]: last closed flux surface
*[LCTE]: linear coefficient of thermal expansion
*[LFS]: low-field side
*[L-mode]: low confinement mode
*[LP]: Langmuir probe
*[MAST]: Mega Ampere Spherical Tokamak
*[MAST-U]: MAST - Upgrade
*[MSG]: Manufacturing Support Group
*[MCF]: magnetic confinement fusion
*[MCS]: machine control system
*[MHD]: magnetohydrodynamic
*[NaN]: not a number
*[NBI]: neutral beam injector
*[NEA]: Nuclear Energy Agency
*[NSE]: Navier-Stokes equation
*[NSTX]: National Spherical Tokamak eXperiment
*[NSTXU]: National Spherical Tokamak eXperiment Upgrade
*[OH]: Ohmic heating
*[OD]: open divertor
*[PIC]: particle in a cell
*[PCS]: plasma control system
*[PDF]: probability density function
*[PEEK]: poly-ether ether ketone
*[PFR]: private flux region
*[PSU]: power supply unit
*[QCE]: quasi-continuous exhaust
*[RF]: radio frequency
*[RFEA]: retarding field energy analyser
*[RMS]: root mean squared
*[RP]: reciprocating probe
*[SC]: scientific coordinator
*[SL]: session leader
*[SOL]: scrape-off layer
*[STEP]: Spherical Tokamak for Energy Production
*[SXD]: Super-X divertor
*[TCV]: Tokamak à configuration variable
*[TS]: Thomson scattering
*[TLP]: triple Langmuir probe
*[UHV]: ultra high vacuum
*[UKAEA]: United Kingdom Atomic Energy Authority
