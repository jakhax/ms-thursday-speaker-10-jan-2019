
# Malduino, making a super cheap [rubber ducky](https://shop.hak5.org/products/usb-rubber-ducky-deluxe)
USB rubber ducky is a keystroke injection tool disguised as a generic flash drive. Computers recognize it as a regular keyboard and accept pre-programmed keystroke payloads at over 1000 words per minute.

Payloads are crafted using a simple scripting language and can be used to drop reverse shells, inject binaries, brute force pin codes, and many other automated functions for the penetration tester and systems administrator.

At the time of writing this the rubber ducky costed $44.99 and we also could not find a supplier in kenya.

Hence we decided to make our own custom cheap rubber ducky using, [arduino micro](https://store.arduino.cc/arduino-micro), which is based on the ATmega32U4 microcontroller featuring a built-in USB which makes the Micro recognisable as a mouse or keyboard, we bought ours from [Nerokas Engineering](https://store.nerokas.co.ke) at $9.83

Though an arduino based rubber ducky is pretty much a common thing right now, its can still be perceived as an awesome thing to do.

### Writing payloads for the malduin0
1. [Seytonics](http://seytonic.com/) made an awesome js library,[duckduino](https://github.com/Nurrl/Duckuino) which can be used to convert existing [ducky script payloads]() to arduino code which can be loaded to the arduino micro via arduino ide.
2. Search for a payload from the [ducky script wiki](https://github.com/hak5darren/USB-Rubber-Ducky/wiki/Payloads), e.g reverse shell, memory dumps, binary injection and bruteforce attacks, modufy the ducky script for your needs then covert it to arduino code from http://seytonic.com/ducky.
3. Copy arduino code to your arduino ide and flash the firmware to your arduino micro.
4. Disconnect the hook it up to test computer to exploit.