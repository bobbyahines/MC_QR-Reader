# ESP32-CAM Microcontroller QR Code Reader
Exploration of the existing 

--------  

## Introduction and Summary

Recently, I've bumped into a lot more small to medium-sized companies utilizing small digital cameras to take photos of one or more barcodes, and software to "scan" the barcodes visibly present in the photograph. I love barcodes and QR codes as a practical approach to location identity matrices. Two-dimensional barcode technology has been around, and proven robust, for **decades**. The technology has been adopted to a point of ubiquitousness, giving us access to inexpensive and highly efficient parts, breakout boards, and chipsets as well as pre-built devices.

--------  

## Background 

--------  

## A Solution

### Parts:

* [ESP32-CAM](https://www.waveshare.com/wiki/ESP32-CAM)  

    The Espressif (that's where the **ESP** part in their board designations) boards are a powerful product line, and you can use the Arduino IDE to control it with a selection of C and C++ functions or flash it to microPython and use a selection of python's library. This specific board, the ESP32-CAM, is the ESP32-S module supports OV2640 camera and a flash. It has onboard WiFi + Bluetooth support, and can do WiFi video monitoring and WiFi image upload, and also has a Micro SD card slot (up to 4GB). Importantly for most field deployments, it supports sleep modes. Its deep sleep current is advertised as low as 6mA!

* [FT232RL FTDI Programmer](https://www.sparkfun.com/datasheets/IC/FT232R_v104.pdf)  
    While the ESP32-CAM board has a lot of powerful features, it does not have any sort of USB plug interface for serial communications. To solve this, I picked up a programmer board and connected directly to the programming pins.  

### Hardware Configuration:  

I began by soldering header pins onto both the ESP32-CAM board and the FTDI programmer. For prototyping purposes, I'm a fan of adding header pins right away, so that I can pin parts down onto a breadboard. This just minimizes my touching and fiddling with the boards, potentially subjecting them to electrostatic discharge or other damage.  

![Picture of Circuit](https://github.com/bobbyahines/MC_QR-Reader/raw/master/src/common/images/icon48.png "Logo Title Text 1")

Using a small breadboard, I arranged the programmer and ESP board. For future convenience, I built a custom wiring harness for connection. Sturdy connections prevent so much debugging.

### Software Configuration:  

While this hardware configuration supports flashing to microPython, I have chosen Arduino's C/C++ library as I have previous experience with using the Arduino IDE.

#### Install the Arduino IDE

No matter which operating system you are working on, install the IDE by using their downloads page. While some OS have the Arduino IDE listed within their package repositories, most are well out of date. The safest way to ensure this all works is get it direct fromt he source: https://www.arduino.cc/en/Main/Software

### Add the Board to the IDE

There are many manufacturers making small microcontroller boards that are Arduino compatible, so you have to tell the IDE to which board you are going to connect. Espressif keeps its own repositories of packages to add drivers and example code to the Arduino IDE for each of their chipsets. In order to access those packages, you must add the repositories to your Arduino IDE preferences before searching the Board Manager. Preferences is a submenu, and it has a field for adding `Additional Board Manager URLs`.  
  
For the ESP32-based products, add `https://dl.espressif.com/dl/package_esp32_index.json`. Next, go to the `Board Manager...` submenu and filter the library by `esp32`. Only one library will likely present itself for installation.

Once saved, load the `Boards` submenu, and note that a `ESP32 Arduino` submenu is now available. For this project I chose the ES32-CAM AI Thinker board.

--------  

## Conclusion  



--------  

## References/Sources  

* https://randomnerdtutorials.com/projects-esp32/  
