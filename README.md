# JTAG-Search for Raspberry Pi

This is an adaption of Igor Skochinsky's JTAG_Search for mbed to the Raspberry Pi, with additional improvement. Like Igor's, it will only identify TDI, TMS, TCK, TDO. It does not identify the JTAG pins nTRST, RTCK, or others.

## How it's Made

I made a simple Pi-implementation mbed wrapper for DigitalInOut and Bam! (like Chef Emeril Lagasse). That's a spicy meatball.

## How to Compile
wiringPi library must be installed. This can easily be installed from Raspbian: 
`sudo apt-get install wiringpi`

then, simply compile by doing
`make`

## How to Use

It uses wiringPi's GPIO numbering system, see http://wiringpi.com/pins/ for more details.

You must connect your pins starting from wiringPi Pin 0. Make your subsequent connections along with the numbering scheme.

When you're ready to run the application. As an example, let's say you're checking 9 pins:

`sudo ./jtag-find -n 9`

It's that simple.

There's a default pre-programmed delay of half-millisecond (500 uS) from any GPIO write operation. If you want to experiment with other values (in microseconds), use -t.
