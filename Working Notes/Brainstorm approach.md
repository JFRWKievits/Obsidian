Name meeting: Brainstorm approach
Attendees: P. Bogdan, J. Kievits
Date: 29-09-2022 

### Non-network
Input layer of Poisson spikes (using PoissonGroup in Brian2) of certain Hz
Connected 1-to-1 with hidden layer (change to sparse or fully-connected?)
Hidden layer of neurons with an offset current and neuron dependent mismatch (small variations in inter-spike-intervals)
Output a inter-spike-interval vs. neuron index plot 
Output a (gaussian) distribution of inter-spike-intervals

Change threshold voltage for some (or all) neurons
Change mismatch values for some (or all) neurons

Noise types:
- Device mismatch (initiliaze all neurons with small mismatch)
- Time constant could drift (implement in device mismatch?)
- Threshold voltage could drift (which should influence inter-spike-interval as well)

### TID
Fit model to experiment output
- Change in leakage current
- Change in voltage shift

Measure spikes in and spike out
Can we input some spikes in between TID exposures?
Can we see TID is gradually increasing? (In the same physical locations)

### SEE 
Input steady state current into all neurons
Characterize output (averaged inter-spike-interval or number of spikes) per neuron as baseline
Run proton beam test and check output again (and save output)
Turn off proton beam, run again (without resetting circuit) and one final run (and save output) 
Can proton beam also be used for TID testing?

SRIM for penetration depth of particles: http://www.srim.org/SRIM/SRIMLEGL.htm


