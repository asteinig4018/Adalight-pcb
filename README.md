# Adalight-pcb

![pcb](imgs/pcb.jpg?raw=true "PCB")

## About

The purpose of this project was to create a small, compact, minimal PCB that could drive WS2812B LED strips for an Adalight system and similar purposes. It uses the Attiny1614.

The PCB can drive 2 strips from its headers (with the necessary capacitors) and includes 4 other GPIO pins. In addition to status and programmable LEDs, the PCB also contains a serial-enabled USB port. (This USB port does not provide power)


## Pinout
![pinout](imgs/attiny1614pinout.jpg?raw=true "Pinout")

Pins A6 and A7 (2 and 3 in Arduino) are connected to onboard LEDs. A1 and A2 (6 and 7 in Arduino) are connected to the LED headers.

More information on the Attiny1614 can be found [here](https://ww1.microchip.com/downloads/en/DeviceDoc/ATtiny1614-16-17-DataSheet-DS40002204A.pdf)

More information on the USB to UART converter can be found [here](https://ww1.microchip.com/downloads/en/DeviceDoc/20005565C.pdf)

## Schematic

See PDF [here](altium_pcb_project/led_driver.pdf)


## Programming

The Attiny is programmed over UDPI. I used an Arduino Uno and this [library](https://github.com/SpenceKonde/jtag2updi) although it is no longer being maintained. 

## Adalight

As FastLED is not supported by the hardware, I ported the Adalight-FastLED library to work with tinyNeoPixel ([port](https://github.com/asteinig4018/Adalight-FastLED)) which is included in the [ATTinyCore library](https://github.com/SpenceKonde/ATTinyCore)

