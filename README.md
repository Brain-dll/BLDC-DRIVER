# BLDC-DRIVER

## INTRODUCTION
BLDC-DRIVER usually uses for driving brusless DC motor. Brusless DC motor has three input, these inputs connect to coils. Rotor of the motor has permenant magnet,
When inputs are energized, Temporarly magnet are occured and interaction which is between permenant and temporarly magnets poles are occured. You can design two kind driver as half bridge 
and full bridge, actually these drivers are working same priciple but there is one difference between them which is while Full bridge driver can energized one coil, It can unenergized 
opposite pole at the same time. Thus system is more efficient. But Half bridge driver can effect just one coil at the same time. For more understanding, you can observe
below picture:

![Image](/Assets/DC-motor-animation.jpg =500x500)

Above diagram is owned a full bridge driver. Purpose of this project is designing own full bridge motor driver and developing drive algorithim at commercial driver level. Actually, this 
project is first step of orginal drone project. Theese project was planned as two variant, one of them is a bit bigger than other one. Controllers of variants will be different and 
some components will change. Both of variants will be produced and tested.

## ATMEGA88PA VARIANT

### Components

* ATMEGA88PA Controller
* TC427COA Mosfet Driver
* IRLR7843TRPBF Mosfet
* Other passive components