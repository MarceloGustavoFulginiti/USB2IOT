# USB2_IOT
Universal Slave Boards USB Input/Output of Things

This proyect consists of a portable Firmware Libraries in C/C++, cross-compiled to several commercial (and DIY) microcontroller based boards (mentioned as "Slave" board). On the other hand an API library (static and dynamic) is also provided for Windows and Linux for de "Host" machine that runs a real world access application.

The aim is to provide to standard and common Host Machines (as PCs, Portable Devices, etc, with Windows or Linux OSs) several kinds of hardware I/O electrical interfaces to interconnect the real world (PWMs, Ins, Outs, I2C, SPI, Serial, etc) for sensors and actuators.

The link between the Host machine and the Slave board is one (or several) standard USB interface. The access form the application (running in the Host) to the electrical I/Os provided by the Slave board is totally transparent, across a well defined and structured C/C++ API, composed by simple primitives to actuate over the Slave's hardware and initialization of mandatory hardware's parameters (microcontroller's peripherals).

Diferent brands and types of Slave boards and microcontrollers are totally transparent for the API and the application. Each hardware resource of same type is managed in the same way, of course considering the physical and functional limitations in each case (i.e. one board could provide SPI @1MHz and other boards could provide SPI @10MHz).

Of course the first question to arrive in our minds, is how about the latency time from an order executed at the Host's API layer (i.e. a primitive to performa an OutX = ON) and the actual electrical transition from 0V to 5V at the physical pin in the Slave board. Depending of the hardware, latency can be improved in sucessive releases of USB2_IOT.

Therefore, this system is to provide a real world access for Applications implemented with common tools and running in common machines, but not in a Real-Time basis (or zero/very low, predictable/constant latency). However this is sufficient for lots of actual applications or hobbies or prototiping phases.

The project will grow step-by-step incorporating different Host's OSs and Slave's models. The first tentative list is:

Slave Boards (with USB interface):

- Arduino AVR (Atmel's 8 bits Microcontroller).
- Arduino SAM (Atmel's 32 bits ARM Cortex Microcontroller).
- Arduino Compatible PIC32 (Microchip's 32 bits MIPS Microcontroller).
- Arduino Compatible LPC (NXP's 32 bits ARM Cortex Microcontroller).
- ...

Hosts:

- PC x86 Arquitecture / Windows 7/10.
- PC x86 Arquitecture / Linux distributions.
- ...

The Development Environment used for the USB2_IOT is the other project posted here: the "ETBeans", "Embedded Multi Tool Chains for the NetBeans IDE". This project is basically a well structured, easy and documented procedures (and some plug-in) to incorporate in a NetBeans environment, diverse tool chains for each platform of Slave boards and Host machines/OSs. The NetBeans is an multiplatform-multilanguaje Open Source IDE, mantained by ORACLE. The tools chains are GCC/GNU, appropiate to each porting according to the microprocessor core.

The binaries of USB2_IOT Host's side (Dynamic Libraries) can be used to develop any application with any IDE/Language, capable to perform dynamic calls to that libraries (.dll or .so).
