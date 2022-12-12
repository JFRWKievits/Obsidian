## Possible effects
Theamount of charge deposited depends on the product of the path lengthand the LET of the ion. Therefore, one must model the sensitivevolume of the device. That is, you must know the area, depth, andshape of the sensitive region. With this information, the distribution ofpossible path lengths in the device can be modeled. These path lengthdistributions can be expressed in either a differential or an integralform, that is, number of paths of a given length, or number of pathsthat equal or exceed a given length (Petersen, 2011)

The circuit that the device is embedded in determines what the appliedpulse shape must be if it is to appear as a legitimate electrical signal.In most cases, these effects can be modeled by standard SPICE circuitmodeling of the circuit. In some case, there are more complicatedinteractions between the charge collection and the circuit, so that theeffects are better modeled if considered together.It is not always possible to obtain enough information about thedetailed device characteristics to perform electrical modeling. It hasnow become common to base the estimates of device sensitivity onexperimental upset measurements in the laboratory.The prediction of rate effects that occur in space then depends onmodels that include three basic factors: the environment, the device dimensions, and the device sensitivity (Petersen, 2011)



#### SEGR
For thermal SiO2 oxides with the incident ion normal to thesurface, Wheatleyet al.[128] showed that the critical electricfield, Ecr, for SEGR is given by:
![[Pasted image 20220922125923.png]]
where E0 is the breakdownfield of the oxide in the absence ofion exposure in MV/cm, L is the ion LET in,and B is a fitting parameter. Sextonet al.[127] has derived anexpression for B:
![[Pasted image 20220922130032.png]]
where mu1 and mu2 are the mobilities of carriers generated by high field injection and by the heavy ion, respectively, n(V) is the electron density from highfield injection, and K is a propor-tionality constant determined assuming that the density of car-riers is proportional to LET (Schwank, 2008).
![[Pasted image 20220922130402.png]]

![[Pasted image 20220927141559.png]]
Not all scaling trends are negative for SEEs in highly scaledCMOS ICs. For example, power MOS devices are vulnera-ble to single-event gate rupture when an ion of sufficientlylarge LET strikes an insulating layer biased at high electricfield [160], [179]. The critical field for SEGR to occur ina space environment for deviceswith dielectric layers thickerthan∼20 nm is∼5 MV/cm [179]–[182]. This led to significantconcern that highly scaled MOS devices with similarly highoxide electric fields might be unsuitable for use in spacesystems, owing to the risks of SEGR [159]. Fortunately,detailed evaluations of the critical voltage for ion-induced gaterupture show that ultrathin dielectric layers are much morehighly resistant to SEGR than devices with thicker dielectriclayers that are struck by ions of similar LET at similarelectric field [183], [184]. This enhanced resistance to SEGRis observed for MOS devices with ultrathin SiO2gate oxidesor high-Kdielectrics [185], and occurs because energeticcarriers do not scatter efficiently enough in thin layers to leadto ion-induced destruction of the oxide [160], [183]–[185]. (Fleetwood, 2021)

#### Radiation Induced Soft Breakdown (RSB)
Increase in leakage current, dependent on circuit application what effects are (Schwank, 2008).

#### Heavy Ion
The upset rate calculation depends on the paths available in the charge collection region (the sensitive volume). Ordinarily, this region is assumed to be a rectangular parallelepiped (RPP). It leads to two different SEE rate calculations: the RPP model and IRPP model. The principle for the RPP model is very simple: the energy deposited (Edep) by an incident ion in the sensitive volume is estimated and if Edep is greater than the threshold energy, the upset occurs. As incident ions are very energetic, they have very long ranges compared with typical device feature sizes and one can assume that their slowing down is continuous and linear. In that case, the deposited energy Edep, can be expressed simply as:(from ECSS, 2010)
![[Pasted image 20220922134830.png]]
The ion is characterised by its LET. An upset occurs when the incident ion has a LET greater than the threshold LET (LETth). To calculate the upset rate, the LET spectrum of the incident particles is evaluated. It leads to a very simple formula due to Bradfordwhere the upset rate is expressed as a function of the incident LET spectrum and the pathlength distribution:(from ECSS, 2010)
![[Pasted image 20220922134935.png]]
But all these RPP model expressions make the same assumption. The LET threshold of each SV is considered equal to a unique value. Petersen pointed out that sensitivity variations across the device cannot be properly accounted for, if the LET spectrum is not folded with the experimental cross section curves [RDF.1]. In reality the critical LETs of the sensitive nodes are not the same but form a distribution that can be fitted by a Weibull function. To take into account the variation of sensitivity by integrating over a distribution of upset rates corresponding to the variation of cross section versus LET, the Integrated RPP approach (IRPP) is used: (from ECSS, 2010)
![[Pasted image 20220922135039.png]]
![[Pasted image 20220922135058.png]]
![[Pasted image 20220922135122.png]]
![[Pasted image 20220922135138.png]]
Improvements to the calculation method can be made, taking into account the following issues:
- Sensitive volumes are not simply rectangular parallelepipeds.
- Both sensitive volume dimensions and critical charge vary along the cross section curve. The real behaviour can be a mix of inter-cell and intra-cell variations (only the critical charge distribution is taken into account in the IRPP method).
- It is questionable as to whether there is a true saturation over the measured effective LET range, and therefore whether the crosss section saturation can be precisely determined.
- Much better heavy-ion upset rate predictions can be achieved using realistic sensitive thickness data (from ECSS, 2010)


#### Proton
Protons and neutrons rely on indirect ionisation processes (i.e. following nuclear interaction) and therefore the pathlength distribution through a sensitive volume is less meaningful for standard methods of calculating cross section. Instead the SEE rate is determined from the environment proton or neutron fluxes and SEE cross sections: (from ECSS, 2010)
![[Pasted image 20220922135440.png]]
Also possible to determine N by using ion irradiation cross section but this method of calculation is less accurate compared with direct use of experimentally-determined proton or neutron cross sections, and shows error levels of factors of three to ten.

#### Test Considerations
The lateral dimensions of the SV can be calculated from the saturation cross section, σsat (sensitive surface in cm²/bit) and the thickness is often assumed to be of the order of 2μm (funnelling and diffusion are ignored). 2 μm is an approximate value for the thickness of sensitive volumes. It is a historical value based on single event upset studies, but for recent and highly integrated technologies with small geometries, and for new SEE mechanisms, is not always valid. However, it is possible to get a more precise estimation of the actual geometry of the sensitive volume with reasonable physical meanings, from experimental measurements. For instance, variation of the SEE sensitivity with angle of incidence (the “tilt angle”) can bring some useful information on the thickness of the sensitive volume [RDF.1] (ECSS, 2010).

SRIM for penetration depth of particles: http://www.srim.org/SRIM/SRIMLEGL.htm