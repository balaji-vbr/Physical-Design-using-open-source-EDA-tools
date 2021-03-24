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

### **LAB:**

By typing the command **>yosys** in linux terminal we can open the yosys terminal as shown.

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%201/3.png" width = 700>

By typing the command **which sta** the location of the sta will be shown. 

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%201/4.png" width = 700>

The command **git clone** is used for cloning the vsdflow. Which is taken from https://github.com/kunalg123/vsdflow.

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%201/5.png" width = 700>

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%201/6.png" width = 700>

This is the tkcon window in which by typing the command **box** we can view the dimensions of the layout in which the area is also specified.

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%201/7.png" width = 700>

These below figures specifies the percentage ratio of flipflop to total logic.For that to be realized we should go to terminal and change the registry to vsdflow.make a catalog my_picorv32.make three registries ie., source,synthesis,layout.In which the real verilog source document picorv32.v is duplicated into source folder. Number of cells = 13197 and Number of flops = 1613, So the Ratio of flops to total logic = 1317/1613 = 12.22%.

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%201/8.png" width = 700>


## **DAY2**

### **Chip planning strategies and introduction to foundry library cells**

Core is the section of the chip where the fundamental logic of the design is placed. A die ,which consists of core ,is a small semiconductor material specimen on whcih the fundamental circuit is fabricated. A netlist describes the connectivity of a electronic design. <br />

Aspect ratio is defined as ratio of height to width of the core. If the aspect ratio is 1 then the chip is in square shape and if it is 0.5 then the chip is in rectangle shape.

Concepts were also taught on De coupling capacitors, Power planning, Concept of preplaced cells. The labs focussed on floorplanning and calculation of area of the chip.

### **LAB:**

Now first we have to change the directory to vsdflow and after that we have to change it to my_picorv32. After this step we should type the command **qflow display picorv32** by which the tckon windown will open. And now again by typing the command **box** in the tckon window we will be able to calculate the area.

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%202/D2SK4%205.png" width = 700>


## **DAY 3**

### **Design and characterize one library cell using Magic layout tool and ngspice**

On day 3 concepts are taught about <br />
SPICE deck creation for CMOS inverter, SPICE simulation lab for CMOS inverter, Switching Threshold Vm, Layout using only stick diagram, Post layout ngspice simulation and the labs mainly focused on transient analysis and calculation of rise delay and fall delay.

### **LAB:**

Inorder to use the ngspice labs the command ngspice_labs is cloned and the directory is changed to ngspice_labs. For viewing the width of pmos, nmos and wp/wn ratio the inv.spice file is opened using the command **cat**.

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%203/D3SK1%205%2C6%2C7.png" width = 700>

This simulation is done by using the ngspice tool and the command used here is **ngspice inv.spice**. This is DC characheterstics graph and by using the command **leafpad** we can change the width of pmos which is 0.75u. 

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%203/D3SK1%208.png" width = 700>

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%203/D3SK1%2010.png" width = 700>

We can also calculate the risedelay by taking the transfer characteristics of the inverter. Rise delay is the difference between the 20% and 80% of a rising waveform. The same steps are followed by opening the ngspice tool and the command **inv_trans.spice** then the transient analysis is done and the waveform is plotted.

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%203/D3SK1%2011.png" width = 700>

With ngspice the pre layout file is simulated and its transient analysis is observed. The command used here is **ngspice fn_prelayout.spice**. Now the output graph is plotted with 1.25 as the refference of the rising waveform. 

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%203/D3SK2%201%2C2.png" width = 700>

The below figure is used for layout drawing and it is opened using the magic tool. The command magic -T min 2 tech is used to open the layout window where we can draw the layout. Now the tckon window and the layout windown will open and by right clicking the bottom left corner of the box and left clicking the top right corner we can calculate the area.

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%203/D3SK3%203.png" width = 700>

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%203/D3SK3%204.png" width = 700>

Now we'll extract all the files by using the command **extract all** and it is used in the **fn_postlayout.spice**. Now this file does not contain the vdd and gnd information so this details are copied from the prelayout file and pasted here. Now the transient analysis is done for the post layout file and the rising and falling waveforms are obtained.

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%203/D3SK3%205.png" width = 700>


## **DAY 4**

### **Pre-layout timing analysis and importance of good clock tree**

On day 4 concepts were taught on Delay tables, Setup timing analysis and introduction to flipflop setup time, Setup timing analysis using real clocks, Hold timing analysis using real clocks<br />

And the labs mainly focussed on netlist description and transient response of an inverter.

### **LAB:**

Now using the command **cat** change the directory to ngspice_labs and open inv_tran.spice file. Now we can see the input rise slew and fall slew of the netlist description.

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK1%206.png" width = 700>

Now we need to find the rise delay using the same method by running the ngspice with the **inv_tran.spice** file and set the plot to transient analysis. 

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK1%207.png" width = 700>

Now change the output load capacitance to 20fF from 10fF and repeat the same steps to find the rise delay of the waveform using transient analysis.

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK1%208.png" width = 700>

Now to find out the values of slew_upper_hreshold_pct_fall, slew_upper_hreshold_pct_rise and output_threshold_pct_rise, output_threshold_pct_fall open the file using this following location /usr/local/share/qflow/tech/osu018/osu018_stdcells.lib 

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK2%206%2C7.png" width = 700>

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK2%208.png" width = 700>

The information of the cell **invx1** is present here.

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK2%209.png" width = 700>

The information on fall_transition, rise_transition, cell_rise, fall delay are present here

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK2%2010.png" width = 700>

Now change the directory from vsdflow to my_picorv32 and create a flie by leafpad picorv32.sdc. Now type the exact command there create_clock -name clk -period 2.5 -waveform {0 1.25} . Now save the file and create another file by leafpad and type the below commands. <br />
read_liberty /usr/local/share/qflow/tech/osu018/osu018_stdcells.lib  <br />
read_verilog synthesis/picorv32.rtlnopwr.v  <br />
link_design picorv32  <br />
read_sdc picorv32.sdc  <br />
report_checks  <br />

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK2%2011.png" width = 700>

Here we can check the data accquired time and the data receive time.

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK2%2012%2C13.png" width = 700>

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK4%202%2C3%2C4.png" width = 700>

Now type the command set_propogated_clock after performing thes sta on prelayout. Now type the command report_checks in the terminal and check the slack

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%204/D4SK4%205.png" width = 700>


## **DAY 5**

### **Final steps for RTL2GDS**

On the final day concepts were taught on Maze routing-Lees's ALgorithm, Design rule checkDesign rule check, Introduction to IEEE 1481-1999 SPEF fomat, Placement and pre layout STA, Routing and post-route STA

### **LAB:**

Now change the directory from vsdflow to my_picorv32 and by using the command **qflow** perform the synthesis and placement steps and for routing type the command qflowroute picorv32. Now a window will pop up where the routing step will take place. After the routing step is completed perform the sta by typing command qflow sta picorv32 qflow backanno picorv32 for the log file to open and then type leafpad log/sta.log to check the pre layout frequency.

This is how the layout will look like

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%205/D5SK2%201.png" width = 700>

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%205/D5SK2%201.png" width = 700>

To check the post layout frequency type the command **leafpad log/post_sta.log**

<img src = "https://github.com/balaji-vbr/Physical-Design-using-open-source-EDA-tools/blob/main/Images/DAY%205/D5SK2%202.png" width = 700>


## **Acknowledgements**
Mr.[Kunal Ghosh](https://www.vlsisystemdesign.com/about-me/) Co-founder of [VLSI System Design Pvt. Ltd](https://www.vlsisystemdesign.com/).
