Name meeting: Meeting Peter 15
Attendees: P. Bogdan, J. Kievits
Date: 07-12-2022 

### Progress
- Running GUI realtime (depends on speed of GUI)

### Questions
- Periodical health check FPGA? - tail -f nohup.out
- Way around asynchronous logging/reading to same file? - run last completed file
- Transportation boxes for FPGA/T0? - Peter takes care of this
- SEUs in other t0 parameters? (simulate?) - yes possibly, known state that t0 object resets to every loop
- Monitor by reading back t0 object? - not possible, t0 object will be last sent object, all parameters on chip that can influence behavior are reinitialized on function execution

### Tasks 
This week:
- i_offset sweep (also after test)
	- store spikes
	- power measurements (power_test.py)
- dac_family_test.py (loop over A, B & C and record) - most important!
- label chips (eg. 1, 2 and 3)

- Calibration
- SEU finder
- Make directories for different t0 chips to store test data

- Mark beamspot!
