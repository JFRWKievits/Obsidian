Title: Structural Plasticity on theSpiNNaker Many-Core NeuromorphicSystem
Author: Bogdan, Petruţ A. and Rowley, Andrew G.D. and Rhodes, Oliver and Furber, Steve B.
Topic: #neuromorphiccomputing 
Publication date: 2018
Retrieved date: 29-06-2022 

### Background
- [[SpiNNaker]] machine with [[structural plasticity]] and [[spike timing dependent plasticity]] 

### Method
- Implement the model proposed by Bamford et al. (2010) using a novel [[structural plasticity]] framework designed for the [[SpiNNaker]] system
- Make use of the speed-up achieved by running the model in real time on SpiNNaker to explorewhether it is suitable for modeling developmental formation of topographic maps over longer time-scales (section 3.3). 
- Explores the behavior of the network when excitatory lateral connections are replaced with inhibitory ones, revealing the stabilizing effect these have on the network 
- Performs sensitivity analysis on the network to establish an operational range of various parameters.

### Results
- Provides about 10 [[computational model]]s  of [[structural plasticity]] based on literature
- Explains why [[structural plasticity]] is better than [[spike timing dependent plasticity]]
- Requirements for a [[structural plasticity]] mechanism to function along side [[spike timing dependent plasticity]] is to implement three functions: find, add, and remove post-synaptic neurons.
- 

### Data 
- Own research combined with already provided model

### Conclusions
- Biasing the [[spike timing dependent plasticity]] parameters can have a large impact
- 

### Significance
- First time [[structural plasticity]] is implemented in software and hardware

### My Notes
- Difficult to see what [[structural plasticity]] actually achieved