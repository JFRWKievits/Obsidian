Title: Circuits and Systems Simulation-based Fault-Tolerance Analysis of Small Satellite On-Board Computers
Author: Burlyaev, Dmitry
Topic: #radiationeffects #spaceradiation 
Publication date: 2012
Retrieved date: 08-07-2022 

### Background
- TUD MSc thesis on [[radiation effects]] in [[electrical devices]] 
- Goal is to make [[simulation]]

### Method
- Proposes a novel [[simulation]]-based statistical approach to assist the [[satellite]] designers in performing OBC [[fault-tolerance]] analysis based on high-level system [[computational model]] and an object-oriented [[fault injection]] mechanism
- Covers the implementation of the proposed [[simulation]] framework which includes the OBC and fault modeling. The fault models are based on the conducted [[radiation environment]] analysis. The range of software and hardware fault detection and [[mitigation strategies]] are investigated as [[case studies]]

### Data
- Uses [[SPENVIS]] for [[radiation environment]] and [[Total Ionising Dose]] expected for different [[orbit]]s
 ![[Pasted image 20220708101811.png]]
- Uses [[SPENVIS]] for [[Linear Energy Transfer]] and [[flux]] of particles
- Uses several subcategories for [[Single Event Effect]]s
- Summarizes [[SRAM]] and [[DRAM]] [[Total Ionising Dose]] and [[Single Event Effect]] data
- Provides explanation of main [[radiation effects]] in [[electrical devices]] 
- Provides schema for designing for [[radiation effects]] [[fault-tolerance]] ![[Pasted image 20220708104400.png]]
- Provides possible [[mitigation strategies]] on [[architecture]] and [[component]] level:
	- improved material hardness
	- design techniques
	- software methods, or Software Implemented Fault Tolerance ([[SIFT]]) techniques
- Proposes lay-out of system of [[electrical devices]] that [[fault injection]] can be applied to
- Effects of different faults is simulated by changing the output or/and the state of a simulated functional block
	- Output is done at TLM initiator sockets
	- State is limited by the knowledge about the block
- [[SRAM]]/[[DRAM]] [[SEU]] or [[MCU]] are physically dependent on location 
- Possible [[failure modes]] are identified

### Results 
- Case studies of a few different problems:
	- Fibonacci calculation
	- JPEG image compression 
	- Kalman filter of Attitude Determination and Control Algorithm
	- Multidimensional analysis of memory fault consequences

### Conclusions
- Traditional [[fault-tolerance]] analysis of [[COTS]]-based [[satellite]]s is limited due to the hardware unavailability at early development stages and low interpretability of radiation tests. 
- The existing [[simulation]] techniques assume that [[integrated circuit]]-level of used electronical [[components]] is known or propose time consuming complex analytical approaches which are unapplicable in small [[satellite]] industry. 
- This work presents an innovative [[simulation]] approach for the statistical [[fault-tolerance]] analysis of the [[satellite]] OBCs.


### Significance
- The work has been appreciated in Europe and USA where it was presented at ESA4S Symposium and North-Atlantic Testing Workshop in 2012.

### My Notes
- Performed at ISIS
- Perhaps interesting to look at D[[MIPS]] needed for neuromorphic tasks
- [[FPGA]] can be [[SRAM]] or [[Flash]] based
- [[SystemC]]-AMS library should be used for [[analog]] or [[mixed-signal]] systems
