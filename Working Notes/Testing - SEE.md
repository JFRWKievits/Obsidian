## Proton beam testing (from Buchner, 2002)
### Safety
- Sources of dangerous radiation could be the particles in the beam, secondary particles and activated material
- Check what rules the HollandPTC facility uses

## Positioning the DUT
- Check size of beam
- Check size of board
- Check if camera's can be used to monitor supply current
- The energy lost by the protons passing throughthe window material and the air between the window and the DUT must be taken into account atlow proton energies (below 20 MeV).
- The best approach is to useSRRIM2000 to calculate the range of protons with low energies in materials. If the energy loss issignificant, it is advisable to remove the packaging if possible, or get an accurate measure of thethickness and use SRIM2000 to calculate the energy loss.
- To avoid accumulating fluence when the DUT is not operating, the DUT should be turned on andoperating properly before being exposed to the proton beam. For the same reason, the beamshould be turned off before the DUT at the completion of the test.

## Beam parameters
A careful selection of proton beam parameters is required to obtain valid data for predictingSEE rates in space. These include proton energy, flux, and fluence.

**Energy**
If the goal is to be able to predict SEU rates in space, it is necessary to measure the SEU cross-section as afunction of proton energy, from threshold to saturation.  The number of different energies needed depends on the following:
- Available accelerator time and the time to change proton energy
- Budget to pay for accelerator time.
- Maximum energy available from accelerator
- Accuracy of error-rate prediction. For model fitting, number of parameters (Weibull/Bendel) determines number of datapoints
- The use of degraders to change beam energy raises the issue of straggle (spreading resulting energy level)
- Measurements to determine the threshold are complicated by the fact that the cross-section is small and large proton fluences are required for good statistics. Large protonfluences can cause TID damage that will destroy the part well before measurements with good statistics are obtained. In this case it is advisable first to do measurements at high proton energies and then at lower proton energies.

**Flux**
- Determined by the cost of beam time and by the capacity of the test equipment to gather the relevant data
- Minimum flux is given by signal-noise ratio 
- Maximum flux is given by secondary effects (could lead to the system being overwhelmed and not operating properly or heating)
- Good practice suggests that aninitial run be made, and the results used to adjust the flux for subsequent runs.

**Uniformity**
- Beam uniformity is important if the device is comparable in size to the beam
- Can be measured using some type of film

**Fluence**
- Because of margin requirements testing is usually performed at fluences greater than in space.
- There are two approaches to testing:
	- In the first, the fluence or dose is applied in incremental steps and the part tested after each step. This is usually necessary when doing single-event upset (SEU) testing, or TID testing when checking the DUT for damage takes such a long time to complete that after checking the device will have accumulated a significant increment in dose. The TID damage is then plotted as a function of either fluence or dose. The total fluence is determined by statistics. For example, if one is satisfied withdata having statistical error bars of 10%, the fluence should be such that at least 100 SEUs are detected, because the statistical variations typically scale as N0.5. This is sometimes not possible near the SEE threshold where the cross-section issmall and the device might be damaged as a result of proton-induced TID or DD before therequired number of SEE have been logged.
	- The second method involves monitoring the relevant parameters during exposure. This is typically done when testing for single-event latchup (SEL). It may also be done for TID testing by continuously monitoring the leakage current. During SEL testing, it is frequently necessary to turn the beam off while power to the part is being recycled. Failure to do so means additional fluence would be accumulated during a period when the DUT was not sensitive to SEL. One way to avoid this problem is to keep the flux sufficiently low that very little additional fluence is added between the time the part latches and the time the beam is turned off.
	- The maximum fluence isdetermined by the type of test being conducted. For SEE testing, the maximum fluence is set by the desired SEE statistics, whereas for TID and DD testing, the fluence is determined directly by the environment.
- If there are no events, then themaximum fluence to test to is determined by the mission requirements. If the requirementsare not known, testing should stop either after a fluence of 10^11 protons/cm2 or after destruction of the part, which ever comes first.

Range
- Check stopping power and range to see if delidding is necessary (SRIM2000 - stopping power and TRIM)
- Check leftover energy after passing through lid

## Proton SEE testing
**Different SEEs** 
- Charge generated in the gate oxide of a MOSFET can cause single-event gate rupture(SEGR). Similarly, charge generated in the semiconductor, at or near a p/n junction, can causesingle-event effects [SEXT92] [MASS93] such as single-event upset (SEU), single-event latchup(SEL) [JOHN96], single-event transient (SET) [KOGA93], single-event snapback (SESB)[KOGA89] and single-event burnout (SEB) [TITU96]. All these effects can, in principle, occurduring proton testing 

Some parts exhibit great sensitivity to heavy ions, having LET thresholds lower than 15MeV.cm2/mg, yet they have been shown to be insensitive to protons. This has been observed forthe case of SEL.

**Single Event Transients**
Accurate SET testing is only possible if the same conditions are also used during testing asexpected in space. For example, SETs in optocouplers are affected by the output load, whichshould be identical to the actual output load used in the application. [REED98] Furthermore,the SET cross-section enhancement at grazing angle of incidence due to direct ionization byhigh-energy protons is much less than for low-energy protons because low-energy protonshave larger LETs. [REED98] The use of degraders that spread the proton energies should beavoided when looking for enhancement of the SET cross-section at grazing angle ofincidence because it makes it more difficult to identify whether direct ionization plays a role.Because the transients induced by protons are likely to be smaller in amplitude than thoseinduced by ions, it is important to make sure the trigger level of the detection equipment isproperly set. In addition, for later analysis of SET pulse height vs width, all transientscaptured on the oscilloscope should be stored

**Stuck bits**
A stuck bit, also called a hard error, is caused by the localized deposition of sufficient charge to produceinterface states that shift the threshold voltage sufficiently far that the device can no longerswitch. This is a localized TID effect. More recently, stuck bits have also been attributed to protons. While testing memories for SEEs with protons, one should monitor both the stuckbits and the leakage current for total dose damage. Following the observation of excessiveleakage current or stuck bits, the part should be replaced because of TID damage.

**Latchup**
Protons are known to induce latchup in certain circuits, particularly those based on CMOS technology. Therefore, when planning to test these types of devices, precautions should betaken to ensure that the device is not damaged due to latchup during testing. This can bedone by limiting the current with the use of resistors or by setting a limit on the maximumsupply current. Should a SEL occur, it would be necessary to cold reboot the system. If thisis necessary, the beam should be turned off immediately and kept off during the rebootingstage to avoid accumulating fluence when no test is being performed. Also, for latchuptesting the flux is usually kept very low to avoid the accumulation of dose between the timethe latchup is detected and the beam is turned off. Once the device is again operatingproperly, the beam can be turned back on. Therefore, the current to the DUT must bemonitored remotely and the rebooting accomplished either automatically or remotely. As thesupply voltage used for state-of-the-art devices is reduced, theoretical predictions show thatthe threat of latchup decreases. It is nevertheless prudent to test devices for SEL with protonsto confirm that they are latchup free.

**Testing at Speed**
Electronic devices such as logic circuits must be tested at the same speed as that used in space because the error rate cross-section hasbeen shown to be frequency-dependent, i.e., the higher the speed, the greater is the error rate. If the part is operated at a speed lower than intended, an underestimation of the error rate will result.Therefore, the bandwidth of the test setup should be commensurate with the test speed needs and this precludes having the test equipment outside the vault. The test equipment must be placed inthe vault and controlled via an Ethernet or other system that allows remote control

**Number of Devices Tested**
The number of DUTs of the same kind that can be tested will depend on many factors,including their size (which determines how many can be tested at once), beam time available,budget and number of devices available. Frequently, one has to settle for testing a single devicebecause of cost or availability of parts. Generally, 2 devices from the same manufacturer and lotwould be acceptable for SEE testing, although 3 would be preferable. COTS devices, known tohave a large variability in threshold energies, certainly require testing of more than one part.

## Data Analysis
Proper data analysis is an important aspect of proton-induced SEE testing. Proton testing isrequired for predicting SEE errors rates in space and involves the measurement of the proton-induced SEE cross-section as a function of energy. Two different theoretical approaches havebeen used to calculate the energy dependence. The first approach is to perform a Monte Carlocalculation (such as CUPID), which will not be discussed here. The second is a semi-empiricalapproach based on the energetics of nuclear interactions. There are three different equations thatone can use for fitting the data - the Bendel 1-parameter equation, the Bendel 2-parameterequation and the Weibull equation. The Bendel 1-parameter equation is not as accurate and is nolonger used, particularly if data is available at more than one proton energy. 

The Bendell and Weibull functions all have the same basic shape – a smoothed out stepfunction that has a threshold at relatively low energy followed by a gradual rise to a saturatedvalue at high energies. For the most accurate predictions, it is necessary to obtain thecomplete shape of the SEE cross-section curve as a function of energy. However, the twomost important parameters are the threshold energy and the saturated cross-section. MostSEE cross-section curves resulting from proton testing are saturated at proton energies above100 MeV. This involves a single measurement at energy greater than 100 MeV. In contrast,it generally requires more than one measurement to determine the threshold. Forconfirmation that the measurements agree with the theory, cross-sections could be measuredat additional energies, but the actual number of energy values depends on budget andaccelerator availability

**Bendel 2-parameter Equation**
Modifications to the Bendel one-parameter function involved using two fittingparameters to obtain better agreement.[SHIM89] The resulting two-parameter function isgiven by: 
![[Pasted image 20221018153743.png]]
![[Pasted image 20221018153900.png]]
where S is the proton limiting cross-section. Figure 6.4 shows a comparison of 1-parameter and 2-parameter fits to data foractual devices.[PETE97] The curves have the same cross section at 60 MeV but a good fit tothe data is clearly obtained with only 1 curve. 

**Weibull 4-parameter Equation**
The integral Weibull function can also be used to fit the data and is given by:
![[Pasted image 20221018153728.png]]
where s(8) is the saturated cross-section, E0 is the threshold energy, W is the width of therising portion of the curve and S is the power that determines the shape. Because there arefour variables in the Weibull function, a minimum of four different energy measurementsmust be made, particularly in the vicinity of the threshold where the cross-sections tend to besmall. This approach is limited by the cost of beam time and the possibility of damaging theDUT when cross-sections are measured at energies close to threshold where a large fluence isrequired to obtain a few SEEs. However, it does provide a more accurate fit.

## SEE testing with TID
More often, the test objective is to determine the SEU characteristics of a CMOS deviceto protons, and the unwanted shifts due to ionizing damage to the oxides represent a complicationto the measurement of SEU sensitivity. Prior to conducting proton SEU testing, Co-60 basedtests or some other indication of the device ionizing dose hardness level should be used as a guideto determine the appropriate number of devices to test. In practice, it is best to carefully monitorthe device parametrics during SEU testing and avoid acquisition of data outside the limits ofacceptable performance. In addition, a carefully monitored test and appropriate test plan canreveal the dependence of the SEU behavior on the level of oxide damage due to ionization. Oftenthe cross sections for SEU will increase as the dose increases, and this may influence the relativesensitivity of the device for specific categories of errors (e.g. bit flips from 0 to 1 may be favoredover 1 to 0 –or vice versa- as the part is damaged. The accurate determination of SEE cross sections for important events can require testing of many devices to TID failure levels to get even poor SEE statistics. Such measures may berequired when the SEE may lead to catastrophic failure, when many copies of the same device arepresent on the same satellite, or when many copies of the same device are used in a constellationof identical satellites.

Petersen has pointed out that the total dose sensitivity of a technology can place practicallimitations on the accurate determination of proton SEE cross sections [PETE97]. This can betrue for TID hardened parts where assurances of very low cross sections are needed, but it may bemuch more important for COTS or other unhardened devices for which the TID failure levelsmay be only a few krad(Si). If the TID failure level of a candidate component is on the order of~10 krad(Si), then testing on an individual DUT will be limited to that dose. If protons of ~60MeV are used, this corresponds to a device cross section of ~10-11 cm2. Smaller cross sectionscannot be measured with a single device, although they may be important, especially for hardfailures and disruptive soft error modes.

Recommendations (from Guertin, 2018)
1. Bring a programmer to the remote test facility.
2. Be prepared to collect data sets with anomalies entangled, but only do so if the anomalies are directly caused by SEE. 
3. Anomalies should be treated as bugs in the test code or system until they can be reproduced through isolated beam behavior (i.e., multiple types of test code or specialized code that enables direct examination of the error).
4. Automate operations if possible because procedures for complex devices may be too hard to memorize and carry out during testing.
5. Be careful to monitor for thermal issues—consider powering down devices between runs (and leverage automation to reduce on time).
6. Significant lowering of cross section below 180 nm on commercial devices is not expected based on existing test data (test engineers should test devices below this level and not assume that per-bit cross sections reduce with feature size).
7. Frequency dependence of SEE is not expected to be significant on commercial devices but may be very significant on RHBD devices.
8. Complex operating systems make results difficult to disentangle. They will lower the effective sensitivity and obscure SEEs.
9. Beware of potential errata under use conditions. Many of the conditions caused by radiation during SEE testing may have had limited manufacturer testability and may therefore not operate as intended at the hardware level.
10. The second consideration is the device response as the energy decreases and proton direct ionization becomes a possibility. In general, this becomes a concern for feature sizes at or below 90 nm (although it may contribute at larger feature sizes). It can be seen that the response can be one to two orders of magnitude higher than the flat part of the curve. Unfortunately, for many of the devices we are discussing in this guideline, it may not be possible to obtain good data at low proton energy. For these devices it is recommended that data on parts from the same fabrication line be used to establish the proton sensitivity. If this is unavailable, a conservative bound to the possible low energy behavior can be inserted into the rate calculation tool used to see how sensitive the rate might be and determine if the unknown response is a significant problem. For futher discussion of testing for low energy proton SEE, see Hardness Assurance for Low-Energy Proton-Induced Single-Event Effects, by Dodds

Recommendations (from Buchner, 2002)
1. You should also ask the staff member to explain how to continue arun following a sudden drop out of the beam, which happens on occasion. Following a run, thebeam parameters, including dose, fluence, exposure time, average beam current, etc should berecorded either as a hard copy or on floppy disk. Bring along a storage medium such as a USB to store the file.
2. Check drop in particle energy due to attenuators, foils and air
3. The use of heavy metals in test fixtures should be avoided because they have long radioactivehalf-lives when activated. Aluminum is the material of choice because of its short half-life.
4. The basic message of this section is that using a proton beam to test for TID is rarely cost-effective due to annealing, enhanced low dose rate effects and the need to test multiple devices.Most TID testing is accomplished with gamma rays in a 60Co cell. However, because TID effectsoften occur in conjunction with SEE and DDD, it is important to understand the mechanismsresponsible for TID so that in those cases where, for example, both SEE and TID need to bemeasured, they can be done simultaneously with protons.

## Test plan
Collection of SEE data for characterization should be collected using worst-case conditions. However, many of the SOCs we are examining cannot be exposed to worst-case conditions. These primarily fall into four categories: temperature, voltage, TID exposure, and application use.Actual worst-case conditions should be determined for the real application and translated, if possible, to the test equipment. In many cases this cannot easily be done because it is not possible to force operating voltages, or to ensure that workload is as desired. It is recommended that the radiation test engineer and application engineer attempt to ascertain the different types of problems the device may encounter, and then establish if worst-case conditions are possible, or if nominal conditions provide a sufficient means to evaluate device performance. The actual application need (and therefore the application engineer) should provide general guidelinelins and help establish what parameters of the operating space are actually relevant for use.Temperature should be controlled for SEL. It is known that SEL is more likely to occur when the device is run at elevated temperature. For most of the parts we are examining here, the temperature is likely to be elevated during testing (perhaps as high as 85°C at the surface if thermal management has been altered).Unfortunately, we cannot recommend testing the subject devices at the manufacturer’s specified high temperature unless the device is not physically altered and you can leave the recommended heat sinking in place. Of course if you are using a heat sink, it may not be reasonable to operate at the specified high temperature. In practice this document recommends that the test personnel ensure that the device is not artificially held at a low temperature and that the highest reasonable temperature is applied during SEL testing. Do not allow this to potentially compromise modified test parts, though. The operating voltage when performing SEL testing should be as high as possible, within the device specification. When testing for SEU or SET, the voltage should be as low as possible, within the device specification. In practice it may be impossible to alter the operating voltage of a pre-built board, and it may introduce test artificats due to mismatched voltages between multiple components. This is a side effect of testing components that are part of complex systems. An effort should be made to control the voltage if possible.

The interplay between TID and SEE may have an impact on devices. Methods for determining the impact of TID on SEE testing are discussed in Schwank et al. [33]. Because the SOCs discussed in this guideline may contain many different types of circuits, they may be very sensitive to this interaction. However, most of the devices discussed achieve fairly high TID levels (above 10 krads(Si)), and most missions of interest here require levels below this, so we have not addressed this problem in any depth. Some missions, such as Jupiter orbiters, may need devices that can withstand hundreds of krads. The general approach suggested is to prepare devices with and without the mission TID requirement; then test both to determine if there is a significant change in SEE response. If no major difference is seen, perform most of the testing on devices without TID exposure. The risk here is that SEE testing also effectively adds dose, and so the devices are always a moving target if TID can alter the SEE response. So using devices with low TID exposure is best for ensuring repeatable results.It is important to note that SEE testing exposes devices to TID. This cannot be avoided. Care should be taken to keep the TID incurred to a controlled level. The flight application’s worst-case conditions should be used during testing, if known. Since the flight application is usually not known at the time of testing, this document recommends understanding the SEE sensitivity of the device relating to individual subsystems. From the subsystem sensitivity, an application worst-case assessment can be made by assuming all observed operational problems can occur on the flight application.Single event gate rupture (SEGR) and single event burnout (SEB) are possible in the transistor structures in SOCs. These event types are most likely when there is high bias applied to transistors, near their maximum rating. In order to test for these, specification maximum voltage should be applied to power rails and IO pins. End of life radiation performance is also a consideration when designing a test. This is typically part of a qualification effort, rather than general radiation charactereization. This guideline is focused on radiation characterization, but we can provide some recommendations. It is expected that all SEE phenomena will be worst case at either beginning or end of life. Thus it is recommended to consider both fresh and aged devices for the test matrix used in SEE testing.Finally, for some SEEs, high clock rate is worst case. While for others, low clock rate (or static condition)is worst case. It is generally not possible to establish which is worst case for a specific SEE type, so high and low frequency (or no clock) should be considered for test planning. It should be noted, however, that this effect is relatively minor in most cases and may be extraneous to the test plan if not required by the application

The implementation of a test algorithm will leave the test device vulnerable to SEU in planned and unplanned regions. The structure of the test algorithm will impact how events are observed and may be important for event counting. It is important to know what the time-model is for any desired upset sensitivity measurement and its corresponding algorithm. At the same time it is important to understand the way in which upset sensitivity of unintentional targets works.When testing, there are three types of targets typically built into test algorithms. The first type comes from the test algorithm where an operation is performed and the result is checked immediately. In this case the portions of the device relevant to that operation are all that are tested, and the result is immediately verified. There is no buildup of errors inside the algorithm. Because of the way this type of test is performed, there is often very little duty cycle to any particular part of the target operation. (For example, if one instruction is tested many times, there may be very little pipeline optimization and the instruction’s six or more clock cycles may be required for every execution resulting in a low effective duty cycle.) The second type of target is the integration target. Here the idea is that a target is sensitive continuously, but that the best approach to the test algorithm is to periodically count errors and reset all the targets to known values.The final type of target structure is an unexpected target that parasitically attaches to all test algorithms in one way or another. Traps, interrupts, and system configuration registers make up some of these targets. An example is a hidden configuration register. Here we end up with targets that can impact how the system operates without being directly observed or observable. By nature, any given test algorithm will be unable to fix these errors, and they can give rise to anomalies in the test data. Because the errors are not fixed, they also contribute to error buildup and over time may begin generating strange results

**Hardware**
1. Utilize inexpensive demonstration kits. Testing generally requires limited functionality as test hardware must be built for each test.
2. Use boards that have the SOC socketed (modern multi-GHz processors are socketed, so performance should not be an issue here). 
3. If the part cannot be removed from the board, ensure the board can fit in any apparatus that will be used to machine or acid etch the DUT.
4. Ensure there are no active components under the DUT.
5. If possible get a board where components are located at least one inch (2.5 cm) from the DUT (so that the board can also serve as a proton test board, or will be ready for high energy heavy ion facilities). 
6. Consider using a different test board for proton and heavy ion tests as the difficulties of each may be more amenable to different boards.
7. If a custom board is being made be very careful about constraining cost as radiation test requirements and desires may result in a design that is significantly outside of normal design methodology.
8. Try to obtain a board where thermal management will be easy. This includes easy changing and positioning of heat sinks.

**Software**
1. Use a test cycle approach that sets up targets, allows upsets, and collects and stores upset information for immediate or later reporting. 
2. Eliminate dependence on operating system—test code should disable operating system control upon execution.
3. Eliminate use of libraries and compilers—the former add code you have no control over, and the latter add structure and register dependence.
4. Limit use of caches for test-critical needs—keep important settings or data off the processor.
5. Store data off of the test board or in nonvolatile memory (NVM) to ensure data recovery.
6. Prepare a safe test code area—a region of memory where the test code can reside away from data and other important code elements.
7. Move the test code to the safe test code area before starting a test algorithm.
8. Service all traps, exceptions, and interrupts—observe and report occurrence. But it is not necessary to properly recover from all events.
9. Prepare the systems that interact with the test device to automatically record all useful data under normal and crash situations—there may be significant complexity which is difficult to carry out correctly by exhausted test engineers.
10. Scrub configuration registers and key information periodically. 
11. Recover I/O devices on error. They may have had their configurations altered.
12. Restart the test cycle after an error occurs.
13. Verify test code integrity after errors—that is, scrub or recopy to remove errors.
14. Use a watchdog monitor to provide an alternate method to recover from a crash.
15. Limit use of memory management units (MMUs).

- falsifiable 

Periodic transfer of SEE and error data is recommended to provide data up to a crash. But the two problems above should be kept in mind. In particular the amount of transferred data during test algorithm execution should be minimized, using error encoding and packing (as opposed to verbose messages).

Possible to perform a single calculation with entire chip and loop to find occurrences? 
Use relevant flight software calculations? (for example timing parameters should allow real-time operation)

Homogeneity in time

Test algorithms should detect errors while running. In a modern running microprocessor instruction-level visibility outside of the processor is not possible. To a limited extent running code can be examined by single stepping and examining cache, memory, and register contents. Thus it is important for the test code to verify that calculations are performed correctly in order to detect upsets.

Sometimes it is simply not reasonable to create custom software for testing of an SOC, or even when custom software is run the results are dominated by exceptions or crashes. In these cases the most useful approach for determining SEE sensitivity is to run standard software and observe how often the execution deviates from what is expected. In this type of testing the best that can be done is to make detailed records of events to enable careful examination, as in Howard et al.

For ground-based testing, the SOC response curve is determined by testing with protons (energies up to 200 MeV for Earth orbiters, though higher energies can be used to simulate some portion of the heavy ion spectrum, or as designated by project requirements) and heavy ions (LETs up to 75 MeV-cm2/mg, or as designated by project requirements).

If this method is not available, at the very least the internal consistency of the dataset being taken should be known (i.e., the cross section vs. LET or energy curve), and the absolute response should be approximately predicted using information about the construction of the device, such as its feature size and the response of similar devices. The second thing is to verify the reproducability of the data by testing with multiple devices or comparing to expected response as a function of LET or proton energy.

To what extent can SEE types be distinguished from eachother?

Low flux improves SNR 

Effective sensitivity can be improved through three primary means. The first is increasing the amount of data taken to increase the signal to be detectable over the noise. The second is improving the event detection. The final method is eliminating anomalies

In most cases the effective sensitivity is going to be the expected beam exposure at each LET. For example, at high LETs guidelines suggest that one test to 1 × 107 cm-2 or 100 events [32]. If events are expected that will result in the device crashing, then the effective sensitivity is likely reduced to about a tenth of the cross section for the device crash (testing with more than 10 crashes for one LET setting is very time consuming). If flux dependence can play a role in device crashes, then a lower flux setting may be desired, with the resulting exposure time being the limiting factor.

Should be able to see if SEEs occur on location immediately. Result of SEEs could be determined later?

Are weights retained after power-cycling? 

Under normal circumstances test engineers will not be able to completely handle all potentially semi-static structures within the device during testing. For this reason, it is recommended that an examination of flux and fluence sensitivity of all algorithms be made before collection of production data. That is to say, it is recommended that algorithms be tested with two fluxes and two fluences, at least 10 times different in size, to ensure no flux or fluence dependence is occurring. If fluence dependence is observed, then lower fluxes and fluences should be preferred unless the dependence can be alleviated.

This information is also discussed earlier in the guideline from a different perspective (section 2.2.6). We briefly touch on the key information here and expand it somewhat.The main thing to understand about flux dependence is that it is very difficult to show that a flux dependent effect is the sole cause of observed upsets. The reason is that upsets that can be seen as flux dependent are hypothesized to be caused by two events (or more) that result in an observable event. An example is an uncorrectable EDAC event in a SECDED EDAC system. Here when an uncorrectable error is observed, it is supposed that this is due to two uncorrelated upsets. To prove this it is not sufficient to show that an increase or decrease in flux corresponds to a similar change in the observation rate for errors. Instead, the flux must be reduced to show that a sufficiently low upset rate can be achieved to meet program requirements with the assumption that the error being due to a true SEE.Many algorithms have flux dependence because of an integration interval. That is, the operation is dependent on a “setup”, “hold”, and then “use” window. The hold period provides an interval for multiple events to occur. These windows tend to have controllable duration, unless they are hidden as discussed in Section 4.4.1. By shrinking or eliminating the window, improved understanding of flux dependence may be gained (though this may be misleading because often the hold window is what provides the duty cycle of the test).Finally, it is important to point out that it is possible testing may not be able to strictly prove the event rate is reduced to the desired level by direct testing. It is instead possible to model the event observations as a combination of a basic SEE sensitivity and a flux-dependent portion. The analysis effort can include a Chi-Squared minimization of a linear function of flux, as in Equation 4-7. 𝜎𝜎(𝜑𝜑)=𝑐𝑐0+𝑐𝑐1𝜑𝜑 (4- 7) where c0 is the constant part of the cross section, and c1 is the linear portion. The c1 term is enhanced in high flux laboratory testing, while c0 is the key component for flight systems since it is not reduced in the space environment and thus dominates the cross section σ. Here the goal would be to show that c0 is below some target value (such as 1 × 10-7cm2). However, when fitting Equation (4- 7) to the data, the uncertainty in c0 will be heavily dependent on the number of observed upsets at low φ. But if many events are seen, then a good measurement of c0 is immediately available without fitting, and if very few are seen, then c0cannot be constrained well. For SEE testing, space rates are often not known within a factor of 2 or more before exposure to the space environment. The difficulties involved in establishing a good set of parameters are such that only a small fraction of required events can be reduced by doing a model fit as discussed. And since the result without modeling would only be slightly altered by this limited reduction, it is not recommended to use this modeling approach.Conversely, if at multiple flux levels the cross section is seen to be approximately constant, then the model approach argues for a very small value of c1 and a non-zero value of c0. This value of c0 is then a basic SEE sensitivity, and will have been established to a reasonable level to rule out flux dependence.

Anomalies should always be attributed to the DUT unless there is a way to show the anomaly is due to some target other than the DUT. It is often very easy to isolate events to the DUT by altering test arrangements and showing the DUT continues to exhibit the anomaly. However, sometimes the number of events is very low. When this happens it is difficult to correlate changes in observed anomaly rates to changes in setup. In practice it is often valuable to isolate events to a particular structure and then focus testing on that structure until the observed SEE is better characterized. This bypasses other elements of anomaly investigation because presumably the observation algorithm can be made arbitrarily good (as needed) to provide event isolation.

One common source of anomalies is stray particles striking devices believed to be protected by shielding or beam collimation. The most common version of this is stray neutrons in proton facilities. One way to examine this case is to shield the DUT from the beam and expose the test chamber or room to the same environment as during a normal beam run. If events are observed at the same rate as when the DUT was not shielded, it is probably a sign of background particle anomalies. Unfortunately, because shielding and collimators can actually produce significant quantities of background neutrons, this is not a definitive test. If shielding the DUT does not significantly impact the event rate, it may be necessary to go further and try to ensure that the DUT is out of the path of neutrons or other particles coming off of the collimator or shielding material during exposre. The DUT can be put out of the beam path, while attempting to put therest of the circuit in the same position as before the DUT was moved out.

Debuggin tools used for:
1. upload test code
2. execute the code in a single-step or breakpoint configuration
3. interrogate registers, caches, and memory
4. break into a running system

Recommendations for the information to be recorded and transferred during testing are given below. 
1. Periodic output of test state (the state often includes some indication of recent SEEs)
2. Full test log with basic operations and key events: test configuration changes, interrupt events, etc.
3. Error log or immediate error output
4. SEE records stored during test and reported after the test completes

The list of recommendations that come out of this section follow.
1. Have a method for establishing the beam and data quality on-site in order to avoid problems during analysis or reporting. 
2. Know how to establish the limiting sensitivity threshold for the device.
3. Have a tiered plan for test goals, which can be flexible to debugging time
4. Determine if flux or event identification improvements can improve testing sensitivity.
5. Cycle the power off and on for every run, unless it is cost prohibitive to do so. Indicate what is done before the start of each run in the test log (power cycle, reset, etc.).
6. Turn off power as often as possible. This differs from 5 in that it is recommended to turn off DUT power as soon as possible after an exposure in order to allow the DUT to cool
7. Determine if multiple events are altering your data by varying flux and fluence on semi-static tests, and be aware that the test code always has some semi-static portions.
8. Collect data on basic structures (possibly while operating at different duty cycles).
9. Do not use debugging tools as a primary means of sensitizing a DUT.
10. Do use debugging tools to examine anomalies and identify software bugs.
11. Understand EDAC systems.
12. Report worst-case numbers with caveats that EDAC improves things – force the project to document their EDAC usage before assuming it.
13. Bring a software person to the test.
14. Record anomalies and details about the anomalies.
15. Analyze anomalies with both hardware and software debugging tools.16.If anomalies do not impact key data or cast doubt on understanding of device operation, do not be led astray by detailed examination.

thermocouple can be used to measure the temperature. For the newer processors, a routine can be developed to read out the processor’s junction temperature.

The following method was adapted by the NASA JPL group to test the registers in the Motorola PowerPC microprocessors [17]. In this method the loop performed the following steps for testing of General Purpose Registers (GPRs) in the Motorola PowerPC: 
1. Load a GPR with the operand 0x55555555 (multiplicand). 
2. Load the next GPR with operand 0x2 (multiplier). 
3. Multiply the registers together and write the result into the first register. 
4. Increment the register pointer (now the second becomes the multiplicand and a third GPR is the multiplier) and repeat steps 1 to 3 until all the GPRs hold multiplication results. 
5. Read the entire GPR and check that the result agrees with expected value of 0xaaaaaaaa. 
6. If not, then log the result to external memory as a strip chart (to be utilized in off-line analysis). 

This test has three possible outcomes: 
8. The test passes and no upset is recorded. 
9. The results do not match the expected value, but only one or two bits are wrong so this is counted as a register upset. 
10. The result does not match the expected value, but many bits are erroneous, which is counted as a processing unit upset because it occurred, for example, in the Arithmetic Logical Unit (ALU) or in the register addressing logic.

Tests of specific software applications can also be done, although the interpretation of such results is less straightforward compared to register tests. Results of operational software can often only be measured using a “go/no-go” criterion, stopping the test whenever the output of the program differs from the expected result. In such cases a series of runs are made, stopping the beam after an error is detected. The processor program is reloaded after each test, restarting the test until another error occurs. The results can only be reported as a total cross section, not a per-bit cross section as for register or cache tests, and require a sequence of test runs. The cross section for the FFT program is much lower, which is the typical result when tests are done with operational software. The reasons for this are related to register usage and visibility. First, even a complex program may use only some of the internal registers and, second, many of the errors that occur in registers will only affect the results if they appear between the time that the register is loaded with information used for the calculation and the time that the step using that information is completed. The latter factor reduces the “visibility” of register errors by factors that are typically between 10 and 100.

During certain SEE tests, the processor can become non-functional—program “hangs” or Single Event Functional Interrupts (SEFIs)—and these types of errors are of extreme concern in applications because they may require complex procedures to restore normal operation. In most cases it is not possible to determine the underlying cause of these malfunctions because there are many possible ways in which processor operation can be disrupted. However, the relative occurrence of “hangs” should be measured and compared to the upset rate obtained for internal registers or other functions of the processor in the space environment. Although “hangs” occurred relatively infrequently in older processors, they occur far more frequently in modern processors that have complex internal architectures. In nearly all cases, recovery from a “hang” condition cannot be done by applying a reset pulse, but instead requires removal of power and cold restart. Consequently, “hangs” are extremely important for modern microprocessors in the space environment.

If flip-chip bonding is used, then the thickness of the chip must be measured to determine if mechanical thinning is required in order to do the tests. Some processors incorporate heat sinks at the back of the die (top of package). The heat sinks may have to be removed or modified in order for the ions to reach the active part of the device.

Test boards must be fabricated (or, if commercial boards are used, adapted) that allow the device to be placed in front of the accelerator beam, with direct access to the device. Unless tests are done with an emulation system, other devices, such as memory, bridge chips, and power control, are placed on the test board. The test board must be thoroughly checked out to ensure that the processor works satisfactorily at the frequency that will be used for the tests. Special diagnostic methods, such as JTAG, require additional connections to the test board. The hardware must include a temperature sensor to measure the operating temperature of the device during operation.

The details listed below must be included, in addition to the part number and date code: 
	1. Size of chip (especially neurosynaptic array) - for determining if beam size can be targeted at neurosynaptic array only or if peripheral systems are also irradiated for minimum beam size
	2. Package type and thickness - for determining if protons can reach the sensitive part of the chip
	3. Thickness of chip - for determining max proton energy deposition in chip
	4. Expected values and variance (ballpark) for neuron parameters (V_th, V_reset, refractoriness, time constants) - for simulation purposes
	5. Maximum rated spike frequency (per neuron) - for determining the influence of transients
	6. Data-to-spike encoder output voltage - for determining the influence of transients 
	7. Fan-in and fan-out of neurons - for determining how SEEs might propagate
	8. Description of digital elements on chip (weights & number of bits) - for determining what SEUs should be taken into account 
	9. Preferred protocol for communicating with chip/board - for determining communication structure. PC in HollandPTC control room will communicate with laptop in radiation room via LAN and TeamViewer. The laptop can be connected to the chip/board.

Finally, processors generate a great deal of heat, particularly when they are operated near maximum frequency. Device temperature should be monitored and reported.

Unlike tests of registers or cache, functional errors are reported on an error-per-device basis. The basic features related to functional errors, hangs, and crashes that need to be reported include: 
	a. Diagnostic results that partially isolate the operating system from the results, including JTAG. 
	b. Fraction of the test runs that result in functional errors and an estimate of the cross section for functional errors compared to the cross section for registers and cache.
	c. Categorization of functional errors by the type of malfunction that occurs. 
	d. Steps required for restoring operation, e.g., application of a RESET pulse or power removal and completing restart.

Using RTOS and bare-metal test?

# Tests
1. Find sweet spot for generating data by tweaking flux and checking errors (non network)
2. Find out how SEE affect a network (synfire chain)
3. Find out how SEE affect a network (synfire chain) with mitigation applied

## Test - 1

#### Goal
Find optimum beam flux for statistical relevance and acceptable behaviour

#### Requirements
1. Innatera processor shall be mounted on (development) board with necessary peripherals
2. Communication from the monitor to the board shall be possible
3. Data output from the board shall contain:
	1. Diagnostic results that partially isolate the operating system from the results (eg. JTAG)
	2. Fraction of the test runs that result in functional errors
	3. Categorization of functional errors by the type of malfunction that occurs. 
	4. Periodic output of test state (the state often includes some indication of recent SEEs)
	5. Full test log with basic operations and key events: test configuration changes, interrupt events, etc.
	6. Error log or immediate error output
	7. SEE records stored during test and reported after the test completes
4. Temperature of the DUT shall be monitored
5. Steps required for restoring operation (eg. RESET pulse, power removal or restart.) shall be reported
6. Boards must be fabricated to allow the DUT to be placed in front of the accelerator beam, with direct access to the device. 
7. If the DUT cannot be removed from the board, ensure the board can fit in any apparatus that will be used to machine or acid etch the DUT.
8. If possible get a board where other components are located at least 2.5 cm from the DUT 
9. Try to obtain a board where thermal management will be easy (e.g. easy changing and positioning of heat sinks)
