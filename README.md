# Physical-Design-using-open-source-EDA-tools
A SOC/Physical Design workshop using open source EDA tools by VSD.

The aim of this repository is to understand the basics of Physical Design which includes floor planning, placement and routing, chip design flow and its applications in the field of VLSI (Very Large Scale Integration) using open source EDA tools. 

The total workshop is divided into 5 days with lab activities on each day as follows

*DAY 1 - Study and review of various components in RISC V based picoSoC.* <br />
*DAY 2 - Chip planning strategies and introduction to foundry library cells.* <br />
*DAY 3 - Design and characterize one library cell using Magic layout tool and ngspice.* <br />
*DAY 4 - Pre-layout timing analysis and importance of good clock tree.* <br />
*DAY 5 - Final steps for RTL2GDS.*



Package QFN - 48 is manufactured by germany labs. The full form of QFN is Quad Flat No leads and the number 48 represents the number of ports of the chip.The package dimensions are 7mm * 7mm. <br />

Picorv32 - It is basically a CPU core which is small size, high clock speed with an native memory interface and an optional IRQ support. <br />

Tools used in this workshop were: <br />

Yosys – for logic Synthesis <br />
Graywolf – for Placement and floor planning <br />
Ngspice- for pre-layout and post-layout simulation <br />
Qrouter – for Routing <br />
eSim - for schematic editor <br />
Netgen – for LVS <br />
Magic – for Layout and Floorplanning <br />
Qflow – RTL2GDS integration <br />
OpenSTA & Opentimer - for Pre-layout and Post-layout Static timing analysis <br />


## **DAY 1**

### **Study and review of various components in RISC V based picoSoC**

RISC V: <br />
RISC-V is an open standard instruction set architecture based on established reduced instruction set computer principles. It is provided under open-source license which gives it a huge advantage when compared to other commercial ISAs.The base RISC-V ISA has a little-endian memory system. The standard is maintained by the RISC-V foundation.

Raven is using a very popular 32-bit RISC-V core (PicoRV32) developed by Clifford Wolf. The core was previously proven with an FPGA implementation and Raven is the first SoC built with it.

### **LAB**

By typing the command **>yosys** in linux terminal we can open the yosys terminal as shown.

D1SK4 3
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%201/3.png" width = 700>

By typing the command **which sta** the location of the sta will be shown. 

D1SK4 4
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%201/4.png" width = 700>

The command **git clone** is used for cloning the vsdflow.

D1SK4 5
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%201/5.png" width = 700>

D1SK4 6
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%201/6.png" width = 700>

D1SK4 7
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%201/7.png" width = 700>

D1SK4 8
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%201/8.png" width = 700>


## **DAY2**

### **Chip planning strategies and introduction to foundry library cells**

D2SK4 5
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%202/D2SK4%205.png" width = 700>


## **DAY 3**

### **Design and characterize one library cell using Magic layout tool and ngspice**

D3SK1 5,6,7
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%203/D3SK1%205%2C6%2C7.png" width = 700>

D3SK1 8
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%203/D3SK1%208.png" width = 700>

D3SK1 10
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%203/D3SK1%2010.png" width = 700>

D3SK1 11
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%203/D3SK1%2011.png" width = 700>

D3SK2 1,2
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%203/D3SK2%201%2C2.png" width = 700>

D3SK3 3
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%203/D3SK3%203.png" width = 700>

D3SK3 4
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%203/D3SK3%204.png" width = 700>

D3SK3 5
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%203/D3SK3%205.png" width = 700>


## **DAY 4**

### **Pre-layout timing analysis and importance of good clock tree**

D4SK1 6
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK1%206.png" width = 700>

D4SK1 7
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK1%207.png" width = 700>

D4SK1 8
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK1%208.png" width = 700>

D4SK2 6,7
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK2%206%2C7.png" width = 700>

D4SK2 8
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK2%208.png" width = 700>

D4SK2 9
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK2%209.png" width = 700>

D4SK2 10
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK2%2010.png" width = 700>

D4SK2 11
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK2%2011.png" width = 700>

D4SK2 12,13
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK2%2012%2C13.png" width = 700>

D4SK4 2,3,4
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK4%202%2C3%2C4.png" width = 700>

D4SK4 5
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK4%205.png" width = 700>


## **DAY 5**

### **Final steps for RTL2GDS**

D5SK2 1
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%205/D5SK2%201.png" width = 700>

D5SK2 2
<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%205/D5SK2%202.png" width = 700>

