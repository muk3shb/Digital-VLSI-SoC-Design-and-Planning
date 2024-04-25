# Digital-VLSI-SoC-Design-and-Planning
# Sky130-Day-1 - Inception of open-source EDA, OpenLANE and Sky130 PDK (24/04/2024 - 25/04/2024)
# How to talk to computers
# Day-1-L1 - Introduction to QFN-48 Package, chip, pads, core, die and IPs
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



  
