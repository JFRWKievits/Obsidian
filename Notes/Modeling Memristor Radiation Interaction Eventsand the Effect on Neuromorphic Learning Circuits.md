Title: Modeling Memristor Radiation Interaction Eventsand the Effect on Neuromorphic Learning Circuits
Author: Dahl, Sumedha Gandharava et al.
Topic: #neuromorphiccomputing #radiationeffects 
Publication date: 2018
Retrieved date: 05-07-2022 

### Background
- [[memristor]] devices are used in [[neuromorphic computing]]
- [[radiation effects]] occur in [[NC hardware]] and [[electrical devices]]

### Method
- An ideal [[memristor]] model is modified to include [[radiation effects]]
- Modeling is done in Cadence Virtuoso design suite using Verilog-A. 
- Simulations include the effect of [[radiation effects]] that could change the state of device or can ionize the device to create e−h+pairs or change the off-state resistance of the device. 
- Combination of these events occurring simultaneously is also studied. Simulation results are compared with the experimental results published in existing research papers. 
- Finally, transient [[simulation]] of a three-input, two-output [[spiking neural network]] with memristive [[synapse]]s is performed. 
- Varying amounts of energy deposited by radiation are modeled.

### Data
- A model of an ideal [[memristor]] is used with characteristics provided
- Several types of [[radiation effects]] are used:
	- State Change Radiation Current
	- Ionization Radiation Current
	- Roff Resistance Change Event
	- Combined Event
	- Radiation Model
- Mentions [[simulation software]] used:
	- Verilog-A
	- Spectre tool in Cadence Virtuoso
- [[NC models]] used ![[Pasted image 20220705103351.png]]

### Results 
- The characteristics of the [[memristor]] with [[radiation effects]] are provided ![[Pasted image 20220705103454.png]]
- It can be noted stronger the radiation intensity more the weights deviate from their desired pattern making [[synapse]]s more and more conductive.

### Conclusions
- ionizing radiation does not simulate any change inthe [[memristor]]
- Radiation also has undesirable effects on [[NC hardware]]. [[radiation effects]] make the connection between two [[memristor]] stronger by changing the state and increasing the synaptic weight
- Further study of neuromorphic circuits are needed to simulate the combination of the radiations effect occurring simultaneously including changing off resistance.
- Simulation of more complex neuromorphic circuitsis needed to emulate the effect of radiation in case when radiation events do not affect all synapses or affect each synapse with different flux or intensity. 
- Simulating the complete neuromorphic circuit in cases where radiation affects both memristor and neurons in the system is also underway. Finally, quantitative comparison of learning processes and pattern recognition accuracy of system pre-and post-radiation event will occur in the future based on the models presented in this work

### Significance
- [[NC models]] in [[simulation]] with [[radiation effects]]

### My Notes

