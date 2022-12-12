Title: Learning behavior of memristor-based neuromorphic circuits in the presence of radiation
Author: Dahl, Sumedha Gandharava et al.
Topic: #neuromorphiccomputing #radiationeffects 
Publication date: 2019
Retrieved date: 16-08-2022 

### Background
- Some research has already been performed on the effects of radiation on [[memristive]] ([[memristor]]) based [[NC hardware]]
- Generally, experimental studies lead to inconclusive results due to the radiation effects being dependent on multiple factors

### Method
This study uses the non-linear drift [[memristor]] model modified ([[Cadence Virtuoso]] design suite using [[Verilog-A]]) to capture its behavior under radiation. The modified model is used in the simulation of a feed-forward memristor-based (many-to-one) [[neuromorphic circuit]], which is taught to learn a spatio-temporal pattern by separating correlated and uncorrelated inputs. The circuit is exposed to [[state-altering]] radiation events of different [[flux]], [[intensity]], and [[duration]] during the learning period and the effect on the learning capacity of the network is observed. 
- Section 2 briefly discusses the [[memristor]] model, [[neural network]] [[architecture]], and its learning behavior. 
- Section 3 discusses the [[radiation effects]] on memristors and updated models
- Section 4 presents detailed network simulations with radiation effects. 
- Section 5 concludes that once the radiation event ends, the [[NC circuits]] can resolve the pattern, but requires a longer time depending upon the radiation [[dose]]
- Focuses on modeling widely observed state-altering (decrease in device resistance) behavior in TiO2 memristive devices.
- Radiation is artificially induced in the circuit using a current pulse of 1 ms duration. The current pulse directly changes the state of the memristive device in the modeltomakeit more conductive.

### Data
- Own simulation using model consisting of 25 simulated memristors ![[Pasted image 20220816115457.png]]
- ![[Pasted image 20220816115820.png]]

### Results 
- TiO2 devices consistently show an increase in current (decrease in device [[resistance]]) after [[x-ray]], [[alpha]] or [[proton]] irradiation without affecting the high or low [[resistance]] limits of the devices 
- 10, 20, 25, and 30 current pulses of magnitude μ = 25 μA and σ = 12.5 μA induced 30%, 77%, 90%, and 95% change in [[resistance]] (from off state) of [[memristor]]. Similar changes are also seen in [[physical experiments]].
- As radiation intensity increased the memristors tended to favor a positive change in [[synaptic weight]] for [[spike timing dependent plasticity]] thus forcing artificial correlation.![[Pasted image 20220816125126.png]]
- Model can re-learn the pattern after irradiation through [[STDP]]![[Pasted image 20220816125436.png]]
- Model cannot re-learn pattern after irradiation with highest flux![[Pasted image 20220816125726.png]]
- Longer irradiation leads to longer re-learning ![[Pasted image 20220816125914.png]]
- Longer irradiation leads to longer re-learning ![[Pasted image 20220816130047.png]]
- Learning under exposure of radiation is problematic ![[Pasted image 20220816130239.png]]
- Learning under exposure of radiation is problematic ![[Pasted image 20220816130303.png]]

### Conclusions
- Subject to continued training, the network starts to recover when exposed to short-termradiationthat alters the synaptic states. 
- Since the memristive devices have to cope with the effect of radiation and relearn the pattern, system-learning time increased based on flux, intensity, and length of irradiation.
- The network is able to learn and separate the uncorrelated afferents when the pattern was presented in low flux radiation.
- Future work includes analyzing the [[long-term effects]] of radiation on the pattern learning capability of the network. It may also be useful to incorporate features such as [[recurrent connections]] and [[inhibitory synapses]], which may increase the [[stability]] of the network.

### Significance
- Simulation of [[NC hardware]] under [[radiation]] conditions using [[spiking neural network]]
- Cited only 11 times

### My Notes
- Nice figures but no [[sensitivity analysis]] on influence of [[model parameters]]
- Also extended version available through grant: Impact of Radiation on Pattern Recognition in Memristor-Based Neuromorphic Circuits 
	- Includes [[neuron death]]
		- Neuron death in biology
		- Neuron death in the network is imitated by disabling pre-synaptic neurons randomly during the learning process.
			- Network shows the capacity to recover even when 25% (10) of the non-participating afferents were killed off. 
			- Random/non-selective neuron death occurred in the network, the pattern learning ability degraded rapidly as 10% (10) of the total afferents were disabled and the network becomes unstable at 5% (5) neuron death.
			- The network’s learning ability was not as seriously deteriorated in the case of gradual neuron death as in the case of instantaneous death at 30 s. 
			- In some of the cases of the gradual neuron death, the network was not affected by the neuron death. On the other hand, when all afferents die simultaneously at 30 s, the network did not recover
