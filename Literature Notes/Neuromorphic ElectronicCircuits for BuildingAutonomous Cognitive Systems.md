Title: Neuromorphic ElectronicCircuits for BuildingAutonomous Cognitive Systems
Author: Chicca, Elisabetta
Topic: #neuromorphiccomputing 
Publication date: 2014
Retrieved date: 09-08-2022 

### Background
- Several [[analog]] and [[digital]] brain-inspired electronic systems have been recently proposed as dedicated solutions for fast simulations of [[spiking neural network]]s. 
- While these architectures are useful for exploring the computational properties of large-scale models of the nervous system, the challenge of building [[low-power]] compact physical artifacts that can behave intelligently in the real world and exhibit cognitive abilities still remains open.

### Method
- Review [[NC circuits]] for emulating neural and synaptic dynamics in real time and discuss the role of biophysically realistic temporal dynamics in [[NC hardware]] architectures.
- Review the challenges of realizing spike-based plasticity mechanisms in real physical systems and present examples of [[analog]] electronic circuits that implement them.
- Describe the computational properties of recurrent neural networks and show how neuromorphic [[winner-take-all]] circuits can implement working-memory and decision-making mechanisms.
- Validate the neuromorphic approach proposed with experimental results obtained from our own circuits and systems, and argue how the circuits and networks presented in this work represent a useful set of components for efficiently and elegantly implementing neuromorphic cognition.

### Data
- Proposes different types of circuits that could be used:![[Pasted image 20220809150556.png]]
- Describes a generalized I&F neuron circuit which makes use of the [[DPI]] circuit and which represents an excellent compromise between circuit complexity and computational power.
	- compact, both in termsof transistor count and layout size
	- low power
	- biologically realistic time constants
	- implements refractory period and spike-frequency adaptation, which are key for more complex models

### Results 
- Plasticity mechanisms that induce changes that increase the synaptic weights are denoted as long-term potentiation ([[LTP]]) mechanisms, and those that induce changes that decrease synaptic weights are denoted as long-term depression([[LTD]]) mechanisms
- Can be combined together to formfull networks of spiking neurons.
	- Explains how an [[analog]] hardware [[neuron]] works
	- Explains how an [[analog]] hardware [[synapse]] works
	- Explains how an [[analog]] hardware [[spike-based learning circuit]] works
- Provides experimental results of neuron, synapse and learning circuits

### Conclusions
- presented an in-depth review of such [[NC circuits]] and systems, with tutorial demonstrations of how to model neural dynamics in analog [[VLSI]]. 
- discussed the problems that arise when attempting to implement spike-based learning mechanisms in physical systems and proposed circuit solutions for solving such problems.
- described examples of recurrent neural network implementations that can be used to implement decision making and working-memory mechanisms, and argued how, together with the circuits described in the previous sections, they can be used to implement cognitive architectures. 
- discussed about the advantages and disadvantages of the approach followed (e.g., for the subthreshold regime of operation or for mismatch in analog subthreshold circuits), and proposed system-level solutions that are inspired by the strategies used in [[biological nervous systems]]. 
- provided an assessment of the progress made in the NE field so far and proposed strategies for accelerating it and reaching the ambitious goal of building autonomous neuromorphic cognitive systems.

### Significance
- Proposes circuits and calculations for all major components of [[NC hardware]] and [[NC model]]
- Cited over 400 times

### My Notes
- Francois recommended it
