Name meeting: Meeting Aditya & Alessandra
Attendees:
Date: 07-10-2022 


### Questions
- Main research focus for Innatera?
	- Yes, the outcomes are still desired but some might not be realized
	- AM: we want to obeserve some macroscopic parameters (eg. voltage shift) the question here is really what amount of dose/time has what influence.
	- AD: We have a characterization routine where we can extrapolate some values from. These parameters we can produce. These are approximations. 
	- AM: This is what we want.
	- AD: several days and 
	- PB: These are neuron parameters not component level
	- AD: Possible but needs time for overview. 
- What are the conclusions based on? (experiences/intuition)
	- AD: I used to work with people in radiation. Circuits will definitely go in one direction. A combination of amplifiers will behave similarly. With respect to the thesis, rough aspects of neuron thresholds would be possible to supply. 
	- AD: We can provide some additional details (amount of devices, pmos, nmos and such)
	- AM: Further level of detail is not interesting 
	- AD: Are the same 

### Next steps
- TID modeling:
	- Use SPICE (or Simulink) with GEANT4 (or GRAS)
	- Comparison to literature (similar architectures)
	- Relevant neuron dynamics (equations)?

- SEE modeling (RPP method):
	- Use CREME96 (basic) or SPICE with GEANT4 (or GRAS)
	- Dimensions/layers of transistors/capacitors (approximately)
	- Materials
	- Number of elements on chip 
	- Number of digital elements on chip (256?)

- AM: If we cannot get the circuit diagram, this would be too rough
	- AM: We can think of functional tests
	- AD: We can do some spike in / spike out 
	- AD: SEE fraction to weight fraction
	- AD: If the weight fraction

- AD: Mitigation strategies are useful and can be applied to (TID and SEE already)
	- AD: the amount of time we get for research is limited and we cannot prioritize this
- 
# Outcomes

Overall
- The objectives as stated in the research proposal (ie. radiation model and mitigation strategy) are desirable for Innatera but this might not be attainable within the scope (and time) of a MSc thesis
- The amount of time that is available at Innatera for research is limited and availability will be based on concurrent commercial projects.
- A shift will be made in the research proposal where the modelling of effects will be compressed to accomodate more time for testing and data interpretation at the end of the research:
	- Begin-October 2023: Start radiation hypotheses & mitigation strategies
	- Mid-November 2022: Start TID testing
	- Mid-December 2022: Start SEE testing
	- Begin-January 2023: Midterm 
	- Mid-January 2023: Data Analysis 
	- End March 2023: Thesis Deadline

TID
- The overall idea is that TID effects will push some characteristics of macroscopic behavior (e.g. voltage threshold) in one particular direction. Modeling this TID behavior serves to have some hypotheses about the macroscopic circuit behavior that shall be used for devising the TID tests.
- To develop hypotheses, Joris will use generic circuit characteristics (e.g. pMOS, nMOS, amount of components, etc.) from Innatera as well as existing research on these components.
- Functional TID testing is fairly straightforward so it would make sense to do this first. However, as this process at the TU Delft has not been done before, some care has to be taken in the planning.
- Innatera characterization can yield estimated neuron parameters (from the spike input-ouput characteristics). Depending on the amount of required detail, this process can take a long time.

SEE
- SEE modeling using existing (SEU) methods would result in a too rough approximation of expected effects that is likely impossible to correlate to actual events. 
- The idea is to do functional tests where some spike-in / spike-out model of Innatera can be used to check the behavior and occurence of SEE's.
- The goal would be to have some global metric (e.g. SEE vs. weight fraction) that can be measured and on which hypotheses can be tested. 
- SEE testing is more dynamic and therefore more difficult. It will likely take 2-3 months to teach Joris how to approach this with the Innatera processors. 

Mitigation
- Mitigation strategies are useful to model already as they can be applied to TID and SEE already in both simulation as the tests.
