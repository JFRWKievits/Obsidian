Title: Propagation of cortical synfire activity; survival probability in single trials and stability in the mean
Author: Gewaltig, Marc-Oliver
Topic: #spikingneuralnetworks 
Publication date: 2001
Retrieved date: 11-07-2022 

### Background
- [[synfire chain]] has been introduced before but it is tested here

### Method
- Presents results from network [[simulation]], taking full account of the variability in pulse packet realizations. 
- Repeatedly stimulated a [[synfire chain]] of model [[neuron]]s and estimated activity (a) and temporal jitter (s) of the spike response for each [[neuron]] group in the chain in many trials. 
- The survival probability of the activity was assessed for each point in (a,s)-space. 
- The results confirm and extend earlier predictions based on single [[neuron]] properties and adeterministic state-space analysis

### 
- Own [[simulation]]

### Results 
- Activity propagation in a [[synfire chain]] poses problems:
	- [[temporal jitter]] potentially builds up causing the synfire to cease after a few groups
	- [[spontaneous activity]] may cause [[neuron]]s in a group to be [[refractory]] when the input arrives which may build up and cause propagation to fail 
- Provides [[SNN model]] with equations for [[synfire chain]]:
	- Membrane properties
	- Spike generation
	- Linear membrane properties
	- Post-synaptic currents
	- Synaptic background activity
	- Delay between groups
	- Width of a [[synfire chain]]
	- Length of a [[synfire chain]]
- Observes four distinct modes:
	- initial stimulus was strong and/or concise enough to assure stable propagation of synchronous activity
	- initital stimulus if not strong enough and the activity propagation ceases after only a few groups
- Describes survivability of a spike packet as a function of the number of spikes in the packet and the temporal dispersion (standard deviation)
- There are two possible sources for variability: 
	- measured quantities a and s, which is independent of the dynamics (separation of noise)
	- system dynamics
- Background cortical activity exhibits coherent spatio-temporal structure
- Provides functionality of [[synfire chain]]

### Conclusions
- [[synfire chain]] with 100 [[neuron]]s per group is structurally strong enough to support stable propagation of spiking activity along the chain
- The propagation can be fully described by just two parameters, the number of spikes a in volley and their temporal jitter s.
- Within the right conditions, the survival probability is close to one; outside it, the survival probability rapidly drops to zero
- Findings indicate that the accuracy of activity propagation in the cortical network is precise and robust enough to explain the precision (~1 ms) of experimentally observed spike patterns

### Significance
- In-depth work on [[synfire chain]] recommended by Peter

### My Notes
- Perhaps useful for [[computational model]]
