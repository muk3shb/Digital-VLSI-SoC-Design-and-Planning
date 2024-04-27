# Digital-VLSI-SoC-Design-and-Planning
# Sky130-Day-1 - Inception of open-source EDA, OpenLANE and Sky130 PDK (24/04/2024 - 25/04/2024)
# Sky130-D1-SK1- How to talk to computers
# SKY_L1 - Introduction to QFN-48 Package, chip, pads, core, die and IPs
![1](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/6d0e847e-ccca-4321-b861-dd0b68bc331a)

The field that we are talking about is inside this chip.
Now, If we look inside the chip we see the block Diagram
![2](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/1b2ea9d2-dee8-4beb-9fd1-66dba3711acd)
The block diagram highliths the center of board, which is the processor and along with processor we have various blocks, such as
  1. VCC/GND -  For power supply
  2. ADC
  3. I2C
  4. QSPI1 - Flash
  5. JTAG- UART.
  6. we have SDRAM chip which is external chip, not On chip.

![3](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/b90f96d7-43b6-48cf-9c94-29c84cfe746e)

When we open up the IC, We see a package(i.e chip in outside world).
![4](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/5d7be4ad-38a8-4250-bae3-069afea13e86)
Packages have names like  QFN-48, Where QFN means "Quad Flat No Leads", There are sevral packages that can be found in Internet.
If We have QFN-256 than 256 represents the no.of pins in package.
The chip Size of QFN-48 is 7nm x 7nm (i.e lenth x breadth) and  manufactured by germany xfab. 
The pin  location of this package are all driven by arduino board. 

![5](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/6573b1d8-ebe6-41c1-ba73-e90078910dcf)
The chip sits at the center of package.
![6](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/e508c742-b532-4d04-a535-62658561c67e)

The chip is connected to package and the way it is connected is teremed as "Wire point".
Wire points connect to the boundry of chip we can transmitt all the data from outside world inside the chip using this.
ON OPENING UP THE CHIP We look inside the chip of the processor.
![7](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/87a19745-9959-4113-84fa-0680e35e9920)
![8](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/da6c9e24-3d4b-4933-ac24-7d52746de73d)
This Chip contains 
1. Pads -
   a. you can send signal inside the chip, for ex. like a door from where people go inside and outside.
   b. Any signal can go inside the chip or outside of chip via Pads.

2. Core -
   a. Core is an area where Digital logic blocks are placed  (i.e AND, NAND, MUX etc.)

3. Die - Die is the size of entire chip, remember it not the size of the processor but the size of the chip.

Now, If we take a sample SoC Design here,
![9](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/6a2d1536-5246-4823-a047-855bf2cef5c1)

We see diffrent SoC blocks.
![10](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/011b366c-3d07-4aba-b8df-c54ed8aaf658)
Like PLL,ADC,DAC,SRAM. This block are called a Foundry.
Foundry - All devices depends on foundry, Basically Foundry is a Big factory that has various sets of machine, where chips are manufactured, To design the chip we have to communicate continuously with foundry,
How ? - Foundry provides some interface files, with those files we communicate to foundry this set of files are intellegent documents, which has unique information.
We also have other block that is
![11](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/2102d2cc-90a6-4d0d-8f28-2adb2fc4580e)
Macros are Pure Digital blocks, While IP have some amount of intellegent techniques to build those blocks.

# SKY_L2- Introduction to RISC-V
![13](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/99602620-9c1a-4e0e-916c-1a0dc82ac8d2)

Instruction Set Archietecture(ISA)- Language of computer, The wa in which, we are going to talk to the computer, 

if you have c program which has to run on hardware which got a specific layout, layout here is interior of chip present on laptop, we need to pass info to particular hardware, for this we will follow the following steps
1. first compile the program to assemblly language program
2. from assembly labguage program to binary code format
   currently in the program we have hex formaat in real world it must converted to binary format.
  and finally, this bits executed in this particular layout and we get the desired output.

for example;- if we want to swap two number the proceess goes as per the flow stated above and finally bits get into layout and we get the required output.

there is another interface 
![image](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/4b98bc51-0468-434f-a55b-7c84fa3d6ac2)
that must be present between the risc v and layout is Hardware description language (HDL) so we need to create risc v specifications with some RTL, in ths case it is picorv32
this rtl implement this specification and finally rtl to layout is obtained, this is nothing but standard pnr - rtl to gds flow, finally at the end from user point of view we execute swap program.

 # SKY_L3- From Software application to Hardware
 We have some Application softwares that needs to be run on our hardware which is chip present on laptop.
 ![image](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/c4b05e1d-ee53-4b51-aede-d729990dbba6)
 So we have System software for this purpose which takes the application software code and converts that code to binary language for hardware. 
 ![image](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/0a47c712-4967-4869-a636-8a05a15b0c21)
 The Various components of system software are:
 1. Operating system
 2. Compiler
 3. Assembler
 
Operating sysytem Handels i/o operations, memory, low level system function apart from this it converts the software application to assembly language program,

Operating system works in following flow:
    The code written in programming language feeds to compiler, the compiler than converts that code into instruction format of specific hardware requirements, we have various insruction format for various hardware IP's like for ARM, Intelx86 etc. In this course we have instruction format of RISC-V core, the compiler functions to convert according to those format and genrate the instructions in .exe file which is crucial part Next, the intruction words are fetched by assembler where it converts each individual set of instruction into a binary language and this binary words are then fed to Hardware for there function.


For Example: "Stopwatch APP"

![image](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/6962f07c-582d-403a-a235-043a4d9cca75)

 1. Input to compiler is C program written for Stopwatch Application
 2. This program is fed to compiler where the ouput of compiler is in RISC-V instructon format, so compiler turn the c program code to instruction format. In the Picture shown below the left side is Stopwatch application program in "C" Images right of it are the outputs of compiler which is RISC-V ISA.
![image](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/db3bea62-07e0-4f30-8a8c-d1c73bde9737)

3. The assembler converts those instructions into binary language and the binary words which enters into hardware(i.e chip layout) executes the stop watch application.

In our Course we are focused enirely upon RISC-V Instructions. The encircled part are the RISC-V Instructions.
![image](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/dbda2470-c75f-4801-9fb4-16638c18637b)

![image](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/731243d5-c774-43ff-a723-b9ebd5ce764a)
This RISC-V Instruction are called as RISC-V ISA, which act as a "Interface" between Computer program and Hardware.

![image](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/f0932001-2ffc-49e9-888a-d27593450910)

In the RISC-V Design, The compiler converts the C- program to RISC-V ISA, These Instruction words are then converted to Binary language by going through a set of design flow that is, we use HDL to Genrate the RTL of RISC-V ISA, the code that are written in HDL implements the function of RISC-V than the RTL is synthesized to gate level design and finally netlists are generted for PD.

![image](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/8a6508e0-8950-42ff-8c2b-6c0904e48409)

# SKY130_D1_SK2 - SoC design and OpenLANE
# SKY_L1 - Introduction to all components of open-source Digital ASIC design

Designing Digital ASIC design must have three components from begining, these are
1. RTL Design
2. EDA Tools
3. PDK data
![image](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/8b68e6d3-6110-4028-954b-1c2f43262e87)
We have various open source tool avilable since a decade but before that it was just a dream to automate the ASIC design flow.
For RTL we have - github.com etc
For EDA tools we have - OpenROAD, openLANE etc.
![image](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/a602c6cb-2c0d-4853-a635-5ead6a835bdb)
PDK : Process design kit act as an interface between FAB and the engineers, it greatly emerged after the introduction of structured design methodology for ASIC i.e Lambda rules, This PDK have versions of specifications which which was part of non disclosure agreement of companies, this made the designing of chip very difficult.

Today, with the introduction of Google and Skywater collaboration for FOSS 130nm Prodcution PDK we now have an opensource PDK to complete the Digital ASIC Design via open source.
 Altough it has some limitations and technology oldage.
 ![image](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/db047c1d-eb92-4a5b-a92d-4eb78488ed06)
 Market share of 130nm Process is 6%.
 
![image](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/85c673d9-e03f-4bbb-a8d4-7344051846ba)

we have 130nm Process implemented in Intel Pentium-4. 3.46GHz Processor and RV32i single cycle CPU.
![image](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/8f51d5aa-b0e4-442c-bddf-fcd64ba596bc)
The Methodology of ASIC design is implemted with FLow objective: RTL to GDSII implementation also called as Physical Design Implementation.

# SKY_L2 - Simplified RTL2GDS flow
contents here..

# SKY130 Day 2 - Good floorplan vs bad floorplan and introduction to library cells
# SKY130_D2_SK1 - Chip Floor planning considerations
# SKY_L2 - Utilization factor and aspect ratio
![image](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/0c0f8479-6983-4acc-8123-636b75339caf)

We wil start with basic netlist, we will begin with 2 flip flops 
 1. Launch and
 2. Capture
  we have simple combinational logic between them, our netlist will have only this logic for our example, to identify the width of core and die.
![IMG_0732](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/471fa66d-b2c5-41db-9484-78cb51709585)

We have Following Combinationallogic elements,
 
 A1 - AND gate,01 - OR gate - class of standard cell.
 while,
 FF1 and FF2 - class of registers.


![IMG_0733](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/70e3c303-4e2b-41ce-b274-3b3f8eb9b7de)
THis is the netlist which define connectivity between all components

![IMG_0734](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/f5b4ad70-01f8-4a24-8c2b-581aa9c1529c)
TO determne the dimension of chip we need to determine dimension of logic gates, so we are dependent on the dimension of AND,OR and flip flops, we provide proper length and breadth to the gates.


![IMG_0735](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/04782337-a4a9-421e-b9c9-07f32faf767c)
we have launch block, AND gate and OR gate in particular dimensions.
 
![IMG_0736](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/c0331f30-83d8-4388-a0f4-9bf01d007b62)
Dimension of core and die is given by dimension of standard cell, here we are giving rough dimension of 1 unit, we calculate the dimensionof core by eliminating the wires and by doing this we determine the area occupied by the core.
now, when we put the chip on silicon wafer with help of this dimension, we will determine the area occupied.
 we remove wires and club all of them, now we calculate area, L = 2 units, Breadth = 2units , area = L x B = 4sq. unit
 lets look into core and dies

![IMG_0738](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/63087efc-998d-4ddb-b4e0-b2c7b64467d8)
we implent this die multiple times in silicon wafer to increase throughtput
If we look into wafer we have die which surrounds the core,
![IMG_0739](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/a5d940bc-1b6f-4aa4-82fb-aa9979eb8745)
we put our digital block inside the core and we will calculate utilization fator and aspect ratio.
![IMG_0743](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/28ab9665-9796-4cb6-a73f-1055caf49860)
Utilization factor is givien by Area occupied by netlist / Total area of core, the picture depits the ellaboration of both.
![IMG_0744](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/8d22953a-d616-45b4-a749-80af1220e4f4)
![IMG_0745](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/b85f01de-b997-42d4-9081-5cd6d0f22b16)
![IMG_0745](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/668e0068-31ec-4324-aae3-407075d58170)
 if we put in dimensions, the utilization factor is 100% i.e 1, we cannot put any extra cell in this case, practically we go for 0.5 or 0.6 utilization factor, 

 Aspect ratio = height / width = 2 sq. unit/ 2 sq. units = 1 unit

 whenever Aspect ratio is = 1 it signifies it is square shape other than 1 signifies rectangla shape
![IMG_0747](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/7bb1e7ec-7519-42bb-9673-62c6adf42fac)


Example-2 - here we take dies of double in length but same height.

![IMG_0749](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/660eb062-5f8d-429a-adc0-f3332546cd21)
Now we will put core in this dimension.

![IMG_0750](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/1022255f-e203-412d-99bd-85986324ca2d)
Next, we calculate the utilization factor and Aspect ratio.
![IMG_0751](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/1691fea9-7ac4-4d79-b9fe-5b645c5dfd8d)

![IMG_0753](https://github.com/muk3shb/Digital-VLSI-SoC-Design-and-Planning/assets/71267630/f7015fa8-7dae-43be-ace6-e522c86f50d8)
 we get the Utilization factor = 0.5 units and Aspect ratio as 0.5 units.

 # SKY_L2 - Concept of Pre-place cells

 




 

 

 descrioption ofimage





 Example - 2
 

 
 


    

 

 






  
