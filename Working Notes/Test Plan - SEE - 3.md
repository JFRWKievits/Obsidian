## 1. Objective
Find out how SEE affect a network (synfire chain) with mitigation applied

## 2. Device to be tested
Innatera B0 processor

## 3. Device information
- Innatera B0-processor (with board)
- Part number 
- A neuromorphic processor attached to a development board with peripheral systems
- Mixed-signal neuromorphic processor
- 28 nm node size
- Packaging
- Provenance of the parts (e.g.,lot date code, wafer and assembly lot number, etc.) 
- Preparation needed (decapsulation/delidding, die thinning, etc.)
- Sample size and number of control devices
- Sample selection process

## 4. Sample size
Statistical significance?

Probably two DUTs and one control device (unirradiated)


## 5. Test facility information
HollandPTC in Delft

Proton testing using accelerator beam

## 6. Test setup
#### 6.1 General requirements
test setup
- test equipment
- cabling
- test board schematics
- software
thermal management of the DUT
the physical arrangement of the setup as it will be implemented at the test facility shall be included.

No DUT pins should remain floating: if left unbiased, they should be shorted or grounded to avoid damage to the DUT from charge buildup. See Annex Bfor a discussion of the test equipment. Potential interferences (see Annex A) must be considered when designing the test setup.

#### 6.2 SEL testing capability
Single-event latchup can result in the catastrophic failure of some device types; thus, power supply limiting or power line resistors may be required to prevent a device failure. If mitigation is used,the experimenter shall verify that the mitigation has not distortedthe latchup detection. Test plans shall also include steps for verification that any current limits reached are due to SEL(see 5.2.7). The test system shall incorporate the capability to monitor the occurrence of latchup, as well as the ability to reset the DUT.

#### 6.3 SEB testing capability
Single-event burnout can result in catastrophic failure of the DUT. In some devices, SEB characterization tests can be performed using an SEB circumvention and monitoring circuit such as that shown in Annex C. At the end of protective-mode SEB testing, the protection circuitry shall be removed and the threshold for SEB verified destructively. Verification testing (see 7.7.1.2) is typically performed without SEB circumvention

#### 6.4 SET testing capability
SET sensitivity and characteristics of linear devices are highly dependent on output load conditions. Attention must be given to the test setup, including cabling, test board design, and equipment, to minimize parasitic capacitance and resistance which will reduce the SET amplitude and increase the width, respectively. Parasitics can also introduce oscillations in the SET pulse. Where possible, anactive oscilloscope probe having low capacitanceshould be used.The test setup must be capable of capturing and saving both positive and negative (and bipolar) transients.A minimum SET magnitude and duration of interest should be defined; the test setup should be sensitive enough to measure these minimum SET characteristics.

## 7. Test conditions
#### 7.1 General overview
A test matrix shall be established that encompasses the device, test program, and beam conditions. Tests shall be performed under application-specific conditions or worst-case conditions for the device type(see 5.2.5.3), unless otherwise agreed to by the parties involved inthe test.

#### 7.2 Test matrix
The test matrix must include at a minimum, as applicable:
- Description of the device configuration including:
	- operational mode
	- input pattern or stimulus
	- electrical bias
	- case temperature
	- current-limiting condition
	- frequency or clock rate
	- reset condition
- Beam conditions:
	- energy
	- ion species
	- range
	- LET
	- flux
	- fluence
	- angle(s)of beam incidence

#### 7.3 Worst-case device operating conditions
As a general rule, the worst-case test conditions are as follows:
- SEU (SBU/MBU): minimum operating voltage, maximum clock frequency; if passive elements such as resistors are designed into the integrated circuit, case temperatures resulting in decreased resistance will increase SEU susceptibility (for example, IC devices incorporating lightly-doped polysilicon resistors increase SEU sensitivity with increasing case temperature [7]).
- SET: there is no broadly applicable worst-case operating condition. It must be experimentally determined for a given device.
- SEL: maximum operating voltage and maximum operating case temperature. 
- SEB: maximum reverse-bias voltage and minimum operating case temperature. 
- SEGR: maximum gate bias; if power MOSFET, maximum drain-source bias under maximum off-state gate bias. Temperature is not a primary factor.

## 8. DUT failure criteria
Indicate the basis for designating DUT failure.

## 9. SEE detection methods
The expected error and/or failuremodes shall be provided in the test plan along with the methods to be used for SEE detection. The basis for detecting SEE must be defined by a comparison of the test device response with some reference state(s), or post-irradiation bit patternsor current levelswith the pre-irradiation patternor current levels. Tests of SETs require special techniques whose extent depends on the definitions of the SET and the objectivesand resources of the experimenter: for SETs on the output of linear devices, the oscilloscope trigger setting will be defined either by an application minimum SET pulse magnitude or duration of concern, or to the lowest level possible in order to capture all transients for characterization of amplitude and duration.Test plans should include methods for differentiating failure modes such as, for example,MBU and SEFI, SEL and SEB or SEFI, and SEGR and SEB.

## 10. Beam characteristics
#### 10.1 General overview
In-air testing requiresdetermination of ion energy and range at the surface of the DUT to ensure sufficient penetration range through the charge-collection regionof the device.Whenmaterials are placed in the beam path to vary the beam energy or LET, the test plan shall include determination of degrader thicknesses, air gap between the beam exit port and die surface, etc. required to achieve the target beam characteristics. The test plan shall include ananalysis ofthe impact of thesematerials on the spectrum of energies/LETs at the die surface and/or active region of the device.Test planning must account for the time required for facility personnel to bring the beam to specification from the off condition or from a different beam energy tune, and for switching ion species/energy. These times can vary substantially between facilities. Users should check with the facility to determine what time penalties will be incurred based upon the beam tuning that is anticipated, and work with the facility to optimize the ion selection flow.

#### 10.2 SEE cross section vs LET curve
Ion species and energies shall be chosen to cover the energy or LET range necessary to determine the SEE threshold, saturatedor maximumcross section, and for full device characterization, the shape of the curve between threshold and saturatedor maximumvalue (see 7.6.2). The test plan shall include evaluation of the ion penetration depth in relationship to the deepest sensitive junction, with the goal of maintaining constant LET through the sensitive volume for all angles of incidence to be tested. This evaluation will require awareness of the material and thickness uncertainties for a particular stack-up.Changing the angle to change the effective LET can be useful for SEUand SEL, and insome lateral power or radio-frequency (RF) MOSFETs, for SEB. Effective LET shouldnot be used in devices susceptible to MBUs or SEGR, and does not apply to SEEs in any device whose sensitive volume is deep compared with the extent of its lateral dimensions.

#### 10.3 SEGR and SEB response curves
Likely not necessary

## 11. Dosimetry
The equipment and techniques needed to measure the ion beam flux, fluence, energy, and uniformity must be identified. The equipment and techniques may be provided by the accelerator facility.

## 12. Flux range
The range of heavy-ion fluxes (both average and instantaneous) must be established to provide the valid dosimetry and assure thatall effectson device responseare due to single ion strikes independent of previous ion strikes. For SEE testing a typical ion flux range is 1x103cm-2·s-1to 1x105cm-2·s-1. However, higher fluxes may be acceptable if it can be established that these high-flux conditions do not invalidate the test results due to problems with dosimetry, tester limits, device heating, and/or charge pile-up effects(examples include effects due to accumulation of charge from more than one ion, false MBU counts whenperforming SRAM read-back during irradiation, etc.)in the device under test.It should be demonstrated that the device response as afunction of flux remains linear at the desired test fluxsuch that the event cross section is independent of flux.

## 13. Particle fluence levels
The appropriate particle fluence level is a function of the test particle kinematics, the numberand sizeof device sensitive nodes/transistors,the number of samples to be tested, and the dynamic operationof the device.The total number of particles must be sufficient to establish with a high statistical confidence that all sensitive volume(s) in the DUT have been irradiatedor that for the given mission environmentand number of devices to be flown, the likelihood of a rare event determined from
![[Pasted image 20221101104842.png]]
where sigma is the event cross sectionand, theta is the beam angle of incidence, is acceptably low for the mission risk tolerance. In the equation above,the use of3.7 bounds the cross sectionat 95% confidencewhen no events are measured(see[3] andAnnex A.10). Dynamic operation introduces to geometric-coverage considerations the need for statistically sufficient (for a givenrisk tolerance)state and temporal coverage.Sufficientgeometric and temporal samplingis most critical when establishing the threshold LET where very few eventsoccur. Historically, as suggested in ASTM 1192, an ionfluence of 1x107cm-2has proved adequate. For the region above theonsetthreshold, typically an ionfluence of 1x106or 100 observed errors may be sufficient. More advanced/complextechnologies may require higher fluence due to lower event rates, and 100 non-destructive errors may not be realistic for these smaller cross-section events.For SEGRor SEBtesting, a minimum ion fluence of 5x105cm-2is used for large, discrete devices, though a higher fluence is warranted when device homogeneity is uncertain and/or when substantial part-to-part variability occurs at this minimum fluence. For small, integrated devices,1x107cm-2is recommended as a minimum for SEGR or SEB testing.Higher fluencethan the typical levels given above are required for certain structures. Deep sub-micronCMOS devices with high cell densities such as SDRAMswill require higher fluenceand sampling ofeach cell/sensitive volume may not be practicable[6]. In this case, the per-bit upset cross sectiondefined in clause3shall be scaled. Test structures will require higher fluence to reveal rare events. When selecting a fluence level, dose effects must be considered for the time the DUT is under irradiation

## 14. Accumulated ionizing dose
The total accumulated ionizing dose for the sum of all planned irradiations shall be recorded for each device (see Annex A.4). Estimates of the DUT tolerance to ionizing dose shall be provided.