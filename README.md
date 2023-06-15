# anthonylhill.github.io
 Pi Zero Adapter for Lee Hart's Membership Card

Tags : eclectic retro mishmash fusion retro-futurism anachronism

![kobayashi maru](https://github.com/anthonylhill/anthonylhill.github.io/kobayashimaru.jpg)

As this group’s members know, there is a lot to like about Lee Hart’s Membership Card (MC). It comes in a compact attractive form factor sporting up to 64K of RAM,  a 4 MHz 1802, serial I/O,  and  lots of switches and blinkenzee lights.  Supplied in kit format, it’s a fun build with an amazing amount of documentation, not to mention Lee Hart’s personal support to help you get things running if you have trouble.
Having said all that, after a few months of usage I felt like there was a little more needed if I was going to do any serious programming with the MC.  Toggling in programs with the front panel switches starts out fun but gets old fast.  Programming EEPROMs is a slow process and they cut into the 64K of available RAM.  Adding serial program download capability to a monitor program is a viable option but requires either an EPROM or a fairly long manual program load via switches.   The earlier MC models had a DB25 connector that could be hooked up to an old school printer port (or GPIO in a microcontroller) but that usually meant an ugly ribbon cable limiting distance and cluttering up your workspace.  And the release of the new MC front panel card meant the DB25 went away in favour of six 7 segment LED’s.
So I’ve designed and built a PCB Raspberry PiZero W loader card that’s format compatible with the MC and  inserts in the middle of the Membership card’s two card stack.  That maintains the look and feel of the MC while allowing just thin power cable as the only hookup to the MC.  The built-in Pi Zero contains my complete 1802 development environment ( editor & A18 & source files ) all interface with a few simple scripts to the 1802 itself. 
Features

1.	automation of the MC front panel switches (except Write Protect) for program loading or other high speed intercessor communications between the Pi and 1802.
2.	serial console via Q & EF3 to Pi UART pins 
3.	able to read parallel output from 1802 to LEDs on front panel - useful for debugging and/or  high speed data exchange
4.	Intercepts the –INT signal from  the front panel when Pi is in control
5.	prototype interconnect area with 5v 3.3v GND plus three gpio pins and ef1, ef2, interrupt
6.	two jumpers to allow bypass of MWR and RUN from front panel
7.	form factor & connectors to fit into MC stack
8.	wifi, usb, hdmi, conposite video from pi now imtegrated into MC stavk
9.	pi scripts plus A18 for development and loading of code
10.	power LED
11.	HDMI & USB & wifi
12.	power via Pi wall wart
13.	all-in-one form factor (albeit no altoids tin)
14.	works with either front panel type
15.	3.3v to 5v level conversion as needed
16.	works with our without the front panel card
