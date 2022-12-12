Name meeting: Meeting Peter 14
Attendees: P. Bogdan, J. Kievits
Date: 29-11-2022 

### Progress
- Meeting with Alessandra
	- powerbreakers not necessary (equipment outside of beam can be handled always)
- Improved GUI
	- has SEU and SET (hopefully correct)

### Questions
- Do we have a way to see if errors are occurring in fpga/board?
- What application on FPGA (vivado)?
	- ARM with Linux, applied C
- Xilinx Zynq-7000 SoC ZC706
	- We can periodically get FPGA health
	- DMA errors might be problematic

### Tasks 
- Simulations with different parameters
- Adapt GUI to T0 needs
	- Restart model
	- Restart entire FPGA+T0
	- Timers
	- Make it real-time
	- Hold on to plots