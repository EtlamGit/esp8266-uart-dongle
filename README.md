# esp8266-uart-dongle

A project for an esp8266 dongle for various IoT projects using UART.

Several manufacturers of home devices like air condition use a modified USB
connector as so called Wifi-Module to bring the devices into the manufacurer
cloud. These dongles can be replaced by this project to control your device
in your own cloud.

This project is inspired by https://github.com/dudanov/iot-uni-dongle
As there are no KiCad project files available, I had to rebuild it from scratch.

Other similar projects are:
* https://github.com/ezcGman/mideahvac-dongle


## Main goals

Stay the same as in the original project from Dudanov:

* using popular Wi-Fi module [ESP12-F](https://docs.ai-thinker.com/_media/esp8266/docs/esp-12f_product_specification_en.pdf) based on ESP8266 SoC
* unified design for all types of home devices from different manufacturers
* use of various connectors with a pitch of 2.54 mm and USB
* possibility of swapping the middle signal TX/RX contacts
* IR transmission and receiving via one wire connected to TSOP output
* very small design: PCB size 24.75 x 19 mm

I extended this with my own ideas:

* use only components in JLCPCB Basic or Promotional library
* use AMS1117 LDO
* use 0805 SMD components to allow hand soldering
* add reset pull-up and reset button
* add 100nF capacitor for ESP supply


## SMT assembly at JLCPCB

The [gerber](gerber) directory contains the files necessary for manufacturing
and assembling the board at the [JLCPCB](https://jlcpcb.com) factory.

You may get a warning notice that the USB connector is not present, but that
is intended as you have to solder that manually only when you need it.

Further steps are soldering the ESP module and selecting the TX/RX pin via
solder jumpers.