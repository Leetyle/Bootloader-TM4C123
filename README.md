# Bootloader-TM4C123

Implement bootloader as FOTA on Tiva C (TM4C123)

## ARM Architecture

### Cortex-M4 Diagram

### Cortex-M4 Processor

### Cortex-M4 Register

### Cortex-M4 Instruction Set

### Cortex-M4

## Startup code

Startup code contains minimal set of code required to configure a vector table, initialize memory, copy the boot loader from flash to SRAM, and execute from SRAM.

## References

* [Startup code](http://www.rowleydownload.co.uk/arm/documentation/index.htm?http://www.rowleydownload.co.uk/arm/documentation/arm_crt0.htm)
* [Arm cortex-m4 programmer model](https://www.slideshare.net/MohammedGomaa5/arm-cortexm4-programmer-model)
* [Design of Microprocessor-Based Systems](http://web.eecs.umich.edu/~prabal/teaching/eecs373-f12/)
* [ARM Cortex-M4 Specs](https://www.slideshare.net/IEEESSCSAlexSC?utm_campaign=profiletracking&utm_medium=sssite&utm_source=ssslideview)