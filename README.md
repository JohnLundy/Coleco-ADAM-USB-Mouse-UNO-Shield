# **Coleco ADAM USB Mouse UNO Shield**
### _Compatable with Coleco ADAM and Colecovision systems_

This Coleco ADAM and Colecovision USB Mouse shield for the Arduino UNO was designed for use with the [Coleco ADAM USB Mouse](https://github.com/JohnLundy/Coleco-ADAM-USB-Mouse) software project. This project was inspired by the original ADAM Mouse that is no longer available and wanted to offer a replacement option using modern USB hardware that is easily obtained.

![assembled](https://github.com/JohnLundy/Coleco-ADAM-USB-Mouse-UNO-Shield/raw/main/docs/assembled.jpg)

## Features

- Designed using the popular Arduino UNO Rev.3 and USB HOST Shield hardware
- Easy to assemble with through-hole component soldering
- Compatible with all modern off-the-shelf USB mice as well as wireless mice
- Ability to change mouse sensitivity and delay balance on the fly for better compatibility with a wide range of software titles

## Design Challenges

The ADAM and Colecovision use two separate commons for joystick switch control and neither is connected to true ground. Both commons are strobed with a 350mS pulse width with a low of -0.7v and a high of 2.8v. This requires the use of optocoupler ICs to isolate the controller signals because low signals from the Arduino cannot be directly connected to the ADAM to simulate controller switch closures. This project uses ILQ and ILD optocoupler ICs to accomplish this.

Both systems never had any software titles specifically designed for mouse control. This added an extra layer of complexity to the design to help compensate for the lack of any kind of standard amongst the wide range of software titles. The design choice of using a 10k potentiometer on the analog (A0) line of the Arduino UNO creates a voltage range that can be sensed to manipulate and adjust mouse sensitivity and joystick delay balance on the fly. With extensive testing, this has proven to work very well to compensate for the wide variety of joystick control sensitivities amongst different software titles. A special button to enable/disable a dedicated precision mode was added for ADAM users for paint programs that need precision movements that otherwise wouldn't work for games.

A workaround was also needed for games that required the joystick to be held down during play to work. This is accomplished by pressing the center mouse button to toggle on/off an increased delay to simulate holding the joystick down in any specific direction.

## Hardware Used In This Project

|Part|Source|
| ------ | ------ |
| ADAM Mouse USB Shield (This project) | https://github.com/JohnLundy/Coleco-ADAM-USB-Mouse-UNO-Shield |
| UNO Rev.3 Board ATmega328P with USB Cable or Equivalent | Ordered from Amazon |
| USB Host Shield for Arduino UNO MEGA 2560 or Equivalent *(See Assembly and Important considerations below for proper configuration)* | Ordered from Amazon |
| Colecovision Controller Y Cable Splitter | retrogameboyz on Ebay|
| USB Mouse | Off-the-shelf USB mouse found anywhere |
| 9V Power Supply (Center Positive 5.5x2.1mm) or USB Cable for power | Easy internet search for UNO power supply  |

## Auduino UNO Shield BOM

|Designation|Part Number|
| ------ | ------ |
| R1-R6 - 1K 1/4w Resistor | CFR-25JB-1K0 |
| R7 - 5.6K 1/4w Resistor | CFR-25JB-52-5K6 |
| R8 - 10K Trimmer Resistor | 3362P-1-103TLF |
| D1,D2 - Diode | 1N4148 |
| D3 - Blue LED 3mm | VAOL-3LSBY2  |
| U1 - ILD1 Dual Optocoupler | ILD1 |
| U2 - ILQ1 Quad Optocoupler | ILQ1 |
| J1 - D-Sub 9P Female RA Connector | 2311765-1 |
| S1 -Tactile Switches 6.0x6.0 | SKHHAKA010 |
| Single Row 40-Pin 2.54mm Male Header Strip | 61304011121 |

![PCB_render](https://github.com/JohnLundy/Coleco-ADAM-USB-Mouse-UNO-Shield/raw/main/docs/PCB_render.jpg)

## PCB (Gerbers and Eagle files)

[Gerbers](https://github.com/JohnLundy/Coleco-ADAM-USB-Mouse-UNO-Shield/raw/main/docs/gerbers/UNO-R3_ADAM_USB_Mouse_2021-03-20.zip)

[EAGLE Files](https://github.com/JohnLundy/Coleco-ADAM-USB-Mouse-UNO-Shield/raw/main/docs/EAGLE/EAGLE_ADAM_USB_Mouse.zip)

## Assembly and Important Considerations
Verify both input 3.3V and 5V pads are bridged on USB host shield next to power header. Verify 5V pad is bridged for VBUS power. 

![host_shield_config](https://github.com/JohnLundy/Coleco-ADAM-USB-Mouse-UNO-Shield/raw/main/docs/host_shield_config.jpg)

![assembled_running](https://github.com/JohnLundy/Coleco-ADAM-USB-Mouse-UNO-Shield/raw/main/docs/assembled_running.jpg)

## Loading Code
Follow the installation instructions located in the [Coleco ADAM USB Mouse](https://github.com/JohnLundy/Coleco-ADAM-USB-Mouse) software project.

## License
GNU General Public License v3.0

![have_fun](https://github.com/JohnLundy/Coleco-ADAM-USB-Mouse-UNO-Shield/raw/main/docs/have_fun.jpg)

**Have Fun!**
