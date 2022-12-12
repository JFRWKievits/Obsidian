De-lidding check with Peter

![[Pasted image 20221013161538.png]](Guertin, 2018)

When testing for SEU or SET, the voltage should be as low as possible, within the device specification. In practice it may be impossible to alter the operating voltage of a pre-built board, and it may introduce test artificats due to mismatched voltages between multiple components. This is a side effect of testing components that are part of complex systems. An effort should be made to control the voltage if possible. (Guertin, 2018)

for some SEEs, high clock rate is worst case. While for others, low clock rate (or static condition)is worst case. It is generally not possible to establish which is worst case for a specific SEE type, so high and low frequency (or no clock) should be considered for test planning. It should be noted, however, that this effect is relatively minor in most cases and may be extraneous to the test plan if not required by the application (Guertin, 2018)

As a general rule, the following elements should be employed in any SOC radiation test algorithm [18]:
	1. Use a test cycle approach that sets up targets, allows upsets, and collects and stores upset information for immediate or later reporting. 
	2. Eliminate dependence on operating system—test code should disable operating system control upon execution.
	3. Eliminate use of libraries and compilers—the former add code you have no control over, and the latter add structure and register dependence.
	4. Limit use of caches for test-critical needs—keep important settings or data off the processor.
	5. Store data off of the test board or in nonvolatile memory (NVM) to ensure data recovery.
	6. Prepare a safe test code area—a region of memory where the test code can reside away from data and other important code elements.
	7. Move the test code to the safe test code area before starting a test algorithm.
	8. Service all traps, exceptions, and interrupts—observe and report occurrence. But it is not necessary to properly recover from all events.
	9. Prepare the systems that interact with the test device to automatically record all useful data under normal and crash situations—there may be significant complexity which is difficult to carry out correctly by exhausted test engineers.
	10. Scrub configuration registers and key information periodically. 
	11. Recover I/O devices on error. They may have had their configurations altered.
	12. Restart the test cycle after an error occurs.
	13. Verify test code integrity after errors—that is, scrub or recopy to remove errors.
	14. Use a watchdog monitor to provide an alternate method to recover from a crash.
	15. Limit use of memory management units (MMUs).
