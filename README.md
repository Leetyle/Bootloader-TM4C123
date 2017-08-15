# Bootloader-TM4C123

Implement bootloader as FOTA on Tiva C (TM4C123)

## ARM Architecture

### Cortex-M4 Diagram

![ARM Cortex-M4 Overview](/images/Cortex-M4.png "ARM Cortex-M4 Overview")

### Cortex-M4 Processor

### Cortex-M4 Register

### Cortex-M4 Instruction Set

### Cortex-M4

## Startup code

Startup code contains minimal set of code required to configure a vector table, initialize memory, copy the boot loader from flash to SRAM, and execute from SRAM.

It's important to understand the sequence of the startup.

![Startup](/images/standard-startup-sequenc.png)

1. At hardware reset, the processor fetches the initial stack pointer and initial program counter from the reset vector. Typically the PC then points to the Reset_Handler.
2. The reset handler performs system initialization, initialize the memory and library. Each step can be configured with assembler macros.
3. System initialization is peformed to configure watchdog, initial clock settings or things like enabling the Floating Point Unit (FPU) if present.
4. The bss data (global memory) gets initialized.
5. As last step it calls the library (C Runtime, crt) _start routine. This initializes the runtime/ANSI library. This part then calls the application main() routine.

Each of the steps can be configured with assembler preprocessor macros, more about this later.

[The sequence of the startup](http://processors.wiki.ti.com/index.php/SYS/BIOS_for_Stellaris_Devices)



## References

* [Startup code](http://www.rowleydownload.co.uk/arm/documentation/index.htm?http://www.rowleydownload.co.uk/arm/documentation/arm_crt0.htm)
* [Arm cortex-m4 programmer model](https://www.slideshare.net/MohammedGomaa5/arm-cortexm4-programmer-model)
* [Design of Microprocessor-Based Systems](http://web.eecs.umich.edu/~prabal/teaching/eecs373-f12/)
* [ARM Cortex-M4 Specs](https://www.slideshare.net/IEEESSCSAlexSC?utm_campaign=profiletracking&utm_medium=sssite&utm_source=ssslideview)