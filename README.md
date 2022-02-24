# 6T SRAM CELL

### This Repositery shows basic 6T SRAM cell
1. [Abstract](#Abstract)

2. [Synopsys Custom Compiler Tool Details](#Synopsys-Custom-Compiler-Tool-Details)

3. [Circuit Details](#Circuit-Details)

4. [Circuit Design](#Circuit-Design)

5. [Waveforms](#Waveforms)

6.[Acknowledgement](#Acknowledgement) 

7. [References](#References)

### Abstract
This paper proposes the implementation of a 6T SRAM cell.A SRAM stores 1 bit of data and also explains its READ and WRITE operation and explains the function of how it stores 1 bit in a cell. This SRAM cell is designed with CMOS logic using the synopsys EDA tool.


### Synopsys Custom Compiler Tool Details
The [Synopsys Custom Compiler™](https://www.synopsys.com/implementation-and-signoff/custom-design-platform/custom-compiler.html) design environment is a modern solution for full-custom analog, custom digital, and mixed-signal IC design. As the heart of the Synopsys Custom Design Platform, Custom Compiler provides design entry, simulation management and analysis, and custom layout editing features. It delivers industry-leading productivity, performance, and ease-of-use while remaining easy to adopt for users of legacy tools.


### Circuit Details
  SRAM is Static Random Access Memory, Also known as Read- Write memory, It is a very crucial part of memory in SOCs and ASIC. It constitutes a large percentage of area in the VLSI designs due to the high number of transistors for a single SRAM cell.The need of SRAM is to be stable and robust read/write operation in such a way that it consumes the least power and enhances the on-chip storage capacity.
  
  SRAM takes two design aspects: the power dissipation and propagation delay in reading and writing the value into the SRAM cell. The power dissipated during read and write operation is dynamic power dissipation. It helps to determine the battery life of portable devices. The given circuit demonstrates six transistor SRAM cells, with 4 cross coupled transistors as memory storage cells, and the other two transistors as access transistors.
  
  These access transistors are connected to the bit line and bit line bar that are denoted by “BL & BLB”. And word line here denoted by “WL” is connected to access transistors when the word line is set on, the access transistors can be accessed and similarly when a word line is set off the content of the memory comes set to hold state as the access transistors are turned off, and as a result, the data will remain unchanged in the cell, for the write operation bit line and bit line bar acts as input lines and for reading operation these lines would act as output lines.


### Circuit Design



### Waveforms


### Acknowledgement

1. Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalpghosh@gmail.com
2. Chinmay panda, IIT Hyderabad
3. Sameer Durgoji, NIT Karnataka
4. [Synopsys Team/Company](https://www.synopsys.com/)


### References
