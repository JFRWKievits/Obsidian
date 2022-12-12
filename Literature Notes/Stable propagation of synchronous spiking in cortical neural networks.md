Title: Stable propagation of synchronous spiking in cortical neural networks
Author: Diesmann, Markus and Gewaltig, Marc Oliver et al.
Topic: #spikingneuralnetworks 
Publication date: 1999
Retrieved date: 11-08-2022 

### Background
- The classical view of neural coding has emphasized the importance of information carried by the rate at which neurons discharge action potentials.
- More recent proposals that information may be carried by precise spike timing have been challenged by the assumption that these neurons operate in a noisy fashion –presumably reflecting fluctuations in synaptic input–and, thus, incapable of transmitting signals with millisecond fidelity. 
- Preliminary results have been presented in abstract form

### Method
- Studies the fine-grained temporal response properties of the [[integrate-and-fire]] neuron
- Focuses on spike responses to transient membrane-potentials analogous to [[biology]]
- A [[pulse-packet]] characterizes a spike volley by two parameters: [[activity]], a , and [[temporal dispersion]] ([[temporal jitter]] [[temporal variation]]) s. Activity is defined as the number of spikes in the volley; their temporal dispersion is measured by the standard deviation of the underlying pulse density
 ![[Pasted image 20220812110803.png]]
- Simulations were performed using a leaky-integrator with voltage-threshold model
- Themodel neuron (membrane time constant 10 ms, resting potential-70 mV, spike threshold-55 mV, absolute refractoriness 1 ms, relative refractoriness (t<15 ms) modelled by K-conductances) was supplied with synaptic noise input, reØecting on-going activity in thecortical network (20,000 synapses: 88% excitatory, 12% inhibitory)
- 
### Data
- Measurements of the response of a cortical model neuron to different [[pulse-packet]] inputs in the presence of background activity in simulations
- The neuronal transmission function for transient input activity is defined by the transformation of the input pair (a_in,s_in) into the output pair (alpha,s_out), where alpha is the [[single neuron response probability]].

### Results 
- Duplication of the experiment with identical input [[pulse-packet]]s yielded essentially the same results, confirming that trial-by-trial response variability is due to fluctuations in background activity
- input pair (a_in,s_in) into the output pair (alpha,s_out) results![[Pasted image 20220812111451.png]]
- neither the relationship between input and output activity, a, nor that between input and output jitter, s,  alone determines whether synchronous activity survives
- Also [[model properties]] determine the evolution of the activity:
	- Number of neurons per group (minimum of 90) is needed to maintain precise spike synchrony but is essentially determined by:
		- the ratio of the distance from mean membrane potential to spike threshold
		- the postsynaptic potential (PSP) amplitude ![[Pasted image 20220812112608.png]]
	- differences in axonal or dendritic delays
	- fluctuations in synaptic transfer properties
	- correlated background fluctuations 
- These will not destroy the synchronous transmission, as long as they do not push the network outside the basin of attraction
- Post synaptic potential up slope is important for the adding together of spikes in a volley

### Conclusions
- Here we show that precisely [[synchronized action potentials]] can propagate within a model of cortical network activity that recapitulates many of the features of biological systems. An attractor, yielding a stable spiking precision in the (sub)[[millisecond]] range, governs the dynamics of synchronization. 
- Our results indicate that a combinatorial neural code, based on rapid associations of groups of neurons coordinating their activity at the single spike level, is possible within a cortical-like network.
- in contrast to other studies using this neuron model7,8,weconclude that precise synchronous firing of cortical neurons is feasible, in spite of the membrane time constant of 10 ms or more.
- The notion of [[pulse-packet]]s yields a natural solution to the question of whether the cortical neuron acts as integrator or coincidence detector by embedding these two conceptions in a single framework. The temporal structure of the input determines which of the two aspects is emphasized

### Significance
- First succesful demonstration of [[synfire]] chain

### My Notes

