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


 
    

 

 






  
