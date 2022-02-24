# 6T SRAM CELL

### This Repositery shows basic 6T SRAM cell
1. [Abstract](#Abstract)

2. [Synopsys Custom Compiler Tool Details](#Synopsys-Custom-Compiler-Tool-Details)

3. [Circuit Details](#Circuit-Details)

4. [Circuit Design](#Circuit-Design)

5. [Waveforms](#Waveforms)

6. [Spice Netlist](#Spice-Netlist)

7. [Acknowledgement](#Acknowledgement) 

8. [References](#References)

## Abstract
This paper proposes the implementation of a 6T SRAM cell.A SRAM stores 1 bit of data and also explains its READ and WRITE operation and explains the function of how it stores 1 bit in a cell. This SRAM cell is designed with CMOS logic using the synopsys EDA tool.


## Synopsys Custom Compiler Tool Details
The [Synopsys Custom Compiler™](https://www.synopsys.com/implementation-and-signoff/custom-design-platform/custom-compiler.html) design environment is a modern solution for full-custom analog, custom digital, and mixed-signal IC design. As the heart of the Synopsys Custom Design Platform, Custom Compiler provides design entry, simulation management and analysis, and custom layout editing features. It delivers industry-leading productivity, performance, and ease-of-use while remaining easy to adopt for users of legacy tools.

![custom_compiler](https://github.com/bharath19-gs/6T_SRAM_CELL/blob/main/6T_SRAM/custom_compiler.png)


## Circuit Details
  SRAM is Static Random Access Memory, Also known as Read- Write memory, It is a very crucial part of memory in SOCs and ASIC. It constitutes a large percentage of area in the VLSI designs due to the high number of transistors for a single SRAM cell.The need of SRAM is to be stable and robust read/write operation in such a way that it consumes the least power and enhances the on-chip storage capacity.
  
  SRAM takes two design aspects: the power dissipation and propagation delay in reading and writing the value into the SRAM cell. The power dissipated during read and write operation is dynamic power dissipation. It helps to determine the battery life of portable devices. The given circuit demonstrates six transistor SRAM cells, with 4 cross coupled transistors as memory storage cells, and the other two transistors as access transistors.
  
  These access transistors are connected to the bit line and bit line bar that are denoted by “BL & BLB”. And word line here denoted by “WL” is connected to access transistors when the word line is set on, the access transistors can be accessed and similarly when a word line is set off the content of the memory comes set to hold state as the access transistors are turned off, and as a result, the data will remain unchanged in the cell, for the write operation bit line and bit line bar acts as input lines and for reading operation these lines would act as output lines.


## Circuit Design

The basic 6T SRAM cell basic design

![image](https://github.com/bharath19-gs/6T_SRAM_CELL/blob/main/6T_SRAM/6T_SRAM_schematic.png)

The symbol of 6T SRAM cell with analysis

![symbol](https://github.com/bharath19-gs/6T_SRAM_CELL/blob/main/6T_SRAM/6T_SRAM_analysis.png)

## Waveforms
 
 The transient analysis of the SRAM cell.
 
 1. With BL starting with '0' and BLB starting with '1'
  ![analysis_1](https://github.com/bharath19-gs/6T_SRAM_CELL/blob/main/6T_SRAM/transient_analysis_6T_SRAM.png)
 
 2. With BL starting with '1' and BLB starting with '0'
  ![analysis_2](https://github.com/bharath19-gs/6T_SRAM_CELL/blob/main/6T_SRAM/6T_SRAM_transcient_analysis.png)

## Spice Netlist

```

.global gnd! vdd!
********************************************************************************
* Library          : GSB_6T_SRAM
* Cell             : 6T_SRAM_CELL
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt _6t_sram_cell bl blb gnd_1 q qb vdd wl vt_bulk_n_gnd! vt_bulk_p_vdd!
xm13 qb q gnd_1 vt_bulk_n_gnd! n25 w=0.36u l=0.26u nf=1 m=1
xm14 q qb gnd_1 vt_bulk_n_gnd! n25 w=0.36u l=0.26u nf=1 m=1
xm15 q wl bl vt_bulk_n_gnd! n25 w=0.36u l=0.26u nf=1 m=1
xm16 blb wl qb vt_bulk_n_gnd! n25 w=0.36u l=0.26u nf=1 m=1
xm11 qb q vdd vt_bulk_p_vdd! p25 w=0.36u l=0.26u nf=1 m=1
xm12 q qb vdd vt_bulk_p_vdd! p25 w=0.36u l=0.26u nf=1 m=1
.ends _6t_sram_cell

********************************************************************************
* Library          : GSB_6T_SRAM
* Cell             : 6T_SRAM_CELL_tb
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
xi0 net12 net14 gnd! net1 net2 net9 net10 gnd! vdd! _6t_sram_cell
v1 net9 gnd! dc=1
v9 net14 gnd! dc=0 pulse ( 0 1 0.1n 0.1n 0.1n 5n 10n )
v8 net12 gnd! dc=0 pulse ( 1 0 0.1n 0.1n 0.1n 5n 10n )
v2 net10 gnd! dc=0 pulse ( 1 0 0.1n 0.1n 0.1n 20n 40n )








.tran '10n' '200n' name=tran

.option primesim_remove_probe_prefix = 0
.probe v(*) i(*) level=1
.probe tran v(net1) v(net10) v(net12) v(net14)

.temp 25



.option primesim_output=wdf


.option parhier = LOCAL




```

## Acknowledgement

1. Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalpghosh@gmail.com
2. Chinmay panda, IIT Hyderabad
3. Sameer Durgoji, NIT Karnataka
4. [Synopsys Team/Company](https://www.synopsys.com/)


## References

[1] Design and performance analysis of 6T SRAM cell on different CMOS technologies with stability characterization Shikha Saun1 and Hemant Kumar1

[2] SRAM operation, https://www.iue.tuwien.ac.at/phd/entner/node34.html 
