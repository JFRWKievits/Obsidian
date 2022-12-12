Name meeting: Meeting Analog Team
Attendees: Aditya, Robin, Peter, Joris
Date: 29-09-2022 

Overall it will be very hard to correlate 
- device behavior to circuit dynamics
- circuit dynamics to neural network behavior

It is assumed that Joris will not gain access to any circuit data as this is the main IP of Innatera (and using it to make sense of things is unlikely). However, according to Amir, perhaps an A0 or A1 could be used/investigated as these are already patented.

For TID behavior modelling, only input and output spikes (dirac current pulses) are measured (of the C0 chip). So device characteristics can only be derived from this at a later stage. Therefore, it is difficult to say what the change in threshold voltage is or the induced leakage current. For modelling purposes, it would be easiest to assume some drift in threshold voltage and some change in leakage (of neurons). Experiments would be the easiest way to find these characteristics. Line fitting and using multiple points could then provide some statistical conclusion on TID susceptibility.

For SEE behavior modelling, some information can be provided with respect to chip behavior. Also material and sensitive volume dimensions are okay to share. The general feeling is that it would be possible to say something about SEE behavior by using the (integral) rectangular parallelipiped approach.

For mitigation strategies, it would likely be possible to implement some re-calibration. This could then be tested before and after radiation to see what effects there might be. Mitigation strategies could include averaging or including multiple redundant neurons. 

