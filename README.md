# BLDC-DRIVER

## INTRODUCTION
BLDC-DRIVER is usually uses for driving brusless DC motor. The brusless DC motor has three input, these inputs connect to coils. Rotor of the motor has permenant magnet, 
When inputs are energized, a temporary magnetism is occurred interaction between permanent and temporary magnets poles. As half bridge and full bridge can be designed two type of 
driver. These drivers work at the same principle but there is a difference between them . Full bridge driver can connect a coil to battery and other coil to ground at the same time. 
Thus system can be more efficient. But Half bridge driver can connect just one coil to battery or ground at the same time. You can observe difference of half and full bridge driver 
designs at below picture:

**HALF BRIDGE DRIVER**

![Image](/Assets/HALF.ppm)

**FULL BRIDGE DRIVER**

![Image](/Assets/FULL.webp)

The problem with BLDC drivers is that they don't know the right moment of energizing. To understand when the energizing sequence changes, we must know the rotor current position firstly.
There are two way for determining current rotor position. First one is traditional technic which uses hall effect sensors. According to sensors output, driver can understand current 
moment of changing. To use extra sensors can increase motors cost, connection number and volume. So this makes our boards more complex. Second way is EMF technic. Stator coil has 
star connection, total voltage level of junction point of these coils always have to be zero. According to below picture, When rotor turns around itself total magnetic field of 
star connection be forced to stay at zero. We can call common point of coils as virtual zero. According to EMF graph, we can understand that magnets come to middle of the two coils, 
when unenergized coil cross the virtual zero. Thus we can detect correct moment for energizing next coil.

![Image](/Assets/BLDC-Motor-working.jpg)

Above diagram show full bridge driver structure. Purpose of this project is designing our own a full bridge motor driver and developing drive algorithms at commercial driver level. 
Actually, this project is first step of the orginal drone project. This project was planned as two variant, one of them is a bit bigger than other one. Controllers of variants can 
be different and some components will be able to change. Both of variants will be produced and tested.

## ATMEGA88PA VARIANT
ATMEGA88PA is controller which was produced by microchip company. It is cheap, easily findable and It includes programmable comparator. Thanks to programmable comparator, more space 
can be earned at the board. Flash memory has less space so we can better program it without bootloader. We can earn more memory as programming at register level.


### Components

* ATMEGA88PA Controller
* TC427COA Mosfet Driver
* IRLR7843TRPBF Mosfet
* Other passive components

**Warning : Mosfet driver has to be noninverting, Inverting drivers has PMOS technology so It's working prenciple is vice versa.**

Our schematic design consist of two page. First of them includes controller design and second one includes mosfets, drivers and connectors

**First Page:**

![First_page](/Assets/First_page.JPG)

**Second Page:**

![Second_page](/Assets/Second_page.JPG)

As you can see, some resistors combination was built, purpose of this combination is taking acceptable feedback from driver.