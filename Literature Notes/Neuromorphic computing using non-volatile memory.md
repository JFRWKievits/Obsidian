Title: Neuromorphic computing using non-volatile memory
Author: Burr, Geoffrey W. et al.
Topic: #neuromorphiccomputing 
Publication date: 2017
Retrieved date: 09-08-2022 

### Background
- Scaling of dense [[non-volatile memory]] ([[NVM]]) crossbar arrays to few-nanometer critical dimensions has been recognized as one path to competitive [[neuromorphic computing]].
- Inherent limitations of [[non-volatile memory]] devices are:
	- finite dynamic range
	- imperfect device reliability and variability
	- non-zero programming energy 
- Peripheral circuitry has been proposed for the realization of hybrid [[CMOS]]/[[NVM]] neuromorphic chips
- [[NVM]] device issues have been considered
- Hebbian learning through [[spike timing dependent plasticity]]

### Method
- survey the state of neuromorphic computing using [[NVM]]
	- starting with biologically-inspired spiking neural networks ([[SNN]]) – including those based on the local [[STDP]] learning-rule
- pure [[CMOS]] neuromorphic implementations that do not depend on [[NVM]].
- survey neuromorphic computing work by the type of [[NVM]] device employed as a [[synapse]]
	- [[phase change material]] (PCM)
	- [[conductive bridging RAM]]
	- [[filamentary resistive RAM]]
	- [[non-filamentary resistive RAM]]
	- other types of devices
- Discuss neuromorphic research in which the [[NVM]] device plays the role of the [[neuron]]

### Data
- Other studies and papers

### Results 
- Provides several studies on succesful [[STDP]] implementation
- CMOS devices makes variability less of an isssue at the cost of larger footprint than NVM
- Provides several studies on succesful [[NC hardware]] implementation of PCM, CBRAM, filamentary RRAM and non-filamentary RRAM (and other typers pf devices) for [[neuromorphic computing]] 

### Conclusions
- NVM devices can help implement neuromor-phic systems by offering compact, low-power and efficient ways to integrate alarge number of incoming signals
- Key research advances needed to make progress towards [[NVM]]-based [[neuromorphic computing]]:
- ![[Pasted image 20220809134644.png]]
- PCM can offer small and contiguous conductance increases through partial crystallization, but conductance decrease (melt-quenching of an amor-phous plug) is abrupt. Adaptations using multiple conductances per synapseand periodic corrections have been developed, but are less than ideal. Resistance ‘drift’, or relaxation of the amorphous phase after the melt-quenching inherent inthe RESET step could also be a potential problem for neuromorphic applications.
- CBRAM offers large dynamic range, but the filament formation process tends to be abrupt.
- Filamentary RRAM suffers similar abrupt SET processes with lowerdynamic range, but offer fab-friendly materials and device structures. In bothcases, neuromorphic architectures that can use binary devices offering stochasticprogramming behavior may be useful. However, the end-to-end use case ofscalable architectures that rapidly converge during learning to show best-in-the-world performance on useful problems must be fleshed out and shown to becompelling.
- Non-filamentary RRAM offers truly bidirectional conductance change, butimprovements are needed in linearity of this response, and in scaling devicesdown to small scale to see if low switching voltages, currents and energies are achievable while maintaining sufficient conductance contrast, switching speedand retention characteristics. 
- Other device concepts, including MTJ and car-bon nanotube transistor devices, have also been proposed. However, furtheradvanced device development and/or invention of acceptable schemes to bridgethe deficiencies of each particular class of NVM devices without loss of speed orpower efficiency is likely to be necessary

### Significance
- Proposes new NVM devices for [[NC hardware]] and lists methods with pros/cons

### My Notes

