# BLDC-DRIVER

## INTRODUCTION
BLDC-DRIVER usually uses for driving brusless DC motor. Brusless DC motor has three input, these inputs connect to coils. Rotor of the motor has permenant magnet, When inputs are 
energized, Temporarly magnet are occured interaction between permenant and temporarly magnets poles are occured. You can design two kind driver as half bridge and full bridge, 
actually these drivers are working same priciple but there is one difference between them . When Full bridge driver fixs coil to battery, It can fix opposite coil to ground at the 
same time. Thus system is more efficient. But Half bridge driver can fix just one coil at the same time. You can observe difference of half and full bridge driver designs at below 
picture:

**HALF BRIDGE DRIVER**

![Image](/Assets/HALF.ppm)

**FULL BRIDGE DRIVER**

![Image](/Assets/FULL.webp)

All kind of driver have a problem which is how we can know true time for changing energized coils order. If we wanna know this knowledge, we have to know rotor current position. 
There are two way for determining current rotor position. First one is traditional technic which is use hall effect sensors. According to sensors behaviour, driver can understand 
true time of changing. But this system has some disadvantages. Some of these are when extra sensors are  used in the motors, Motors cost, connection number and volume can increase. 
So this makes more complex our boards. Second way is EMF technic. Due to stator coil has star connection, total voltage level of junction point of these coils always have to be zero. 
According to below picture, When rotor turns around itself total magnetic field of star connection force to keep zero. We can call common point of coils as virtual zero. When we 
analyze EMF graffic, we can understand that magnets come to middle of the two coils at every time, unenergized coil cross the virtual zero. Thus we can understand what time coils 
turn have to be occur.

![Image](/Assets/BLDC-Motor-working.jpg)

Above diagram is owned a full bridge driver. Purpose of this project is designing own full bridge motor driver and developing drive algorithim at commercial driver level. Actually, 
this project is first step of orginal drone project. Thise project was planned as two variant, one of them is a bit bigger than other one. Controllers of variants will be different 
and some components will change. Both of variants will be produced and tested.

## ATMEGA88PA VARIANT
ATMEGA88PA is controller which was produced by microchip company. Advantages of this controller are cheap, easly findable and It includes programable comparator. Thanks to programable 
comparator, we can earn more space for designing. Disadvantage is that flash memory has less area so we should programming without bootloader. we can earn more area of the flash was 
planned with programming register level


### Components

* ATMEGA88PA Controller
* TC427COA Mosfet Driver
* IRLR7843TRPBF Mosfet
* Other passive components

**Warning : Mosfet driver has to be noninverting, Inverting drivers has PMOS technology so It's working prenciple is vice versa.**

Our schematic design consist two page. First of them includes controller design and second one includes mosfets, drivers and connectors

**First Page:**

![First_page](/Assets/First_page.JPG)

**Second Page:**

![Second_page](/Assets/Second_page.JPG)

As you can see, some resistors combination was built, purpose of this combination is taking acceptable feedback from driver.