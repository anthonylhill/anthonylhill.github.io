# PiZero Adapter for Lee Hart's Membership Card
### anthonylhill.github.io

Tags : eclectic retro mishmash fusion retro-futurism anachronism

![kobayashi maru](https://github.com/anthonylhill/anthonylhill.github.io/blob/main/photos/kobayashimaru.jpg)

<table>
    <tr>
        <td>Foo</td><td>bar</td>
    </tr>
    <tr>
        <td>Ddo</td><td>bfr</td>
    </tr>
    <tr>
        <td>DUU</td><td>brtt</td>
    </tr>
</table>

There is a lot to like about [Lee Hart’s Membership Card](http://www.sunrise-ev.com/1802.htm "Click this link") (MC). It comes in a compact attractive form factor supporting up to 64K of RAM,  a 4 MHz 1802, serial I/O,  and  lots of switches and blinkenzee lights.  Supplied in kit format, it’s a fun build with an amazing amount of documentation, not to mention Lee Hart’s personal support to help you get things running if you have trouble.

Having said all that, after a few months of usage I felt like there was a little more needed if I was going to do any serious programming with the MC.  Toggling in programs with the front panel switches starts out fun but gets old fast.  Programming EEPROMs is a slow process and they cut into the 64K of available RAM.  Adding serial program download capability to a monitor program is a viable option but requires either an EPROM or a fairly long manual program load via switches.   The earlier MC models had a DB25 connector that could be hooked up to an old school printer port (or GPIO in a microcontroller) but that usually meant an ugly ribbon cable limiting distance and cluttering up your workspace.  And the release of the new MC front panel card meant the DB25 went away in favour of six 7 segment LED’s.

So I’ve designed and built a PCB Raspberry PiZero W loader card that’s format compatible with the MC and  inserts in the middle of the Membership card’s two card stack.  That maintains the look and feel of the MC while allowing just thin power cable as the only hookup to the MC.  The built-in Pi Zero contains my complete 1802 development environment ( editor & A18 & source files ) all interface with a few simple scripts to the 1802 itself. 

## Features
<ol>
<li>Program loading via override of the MC front panel switches 
<li>Serial console interface between PiZero and 1802 via Q & EF3 to Pi UART GPIO pins 
<li>Able to read parallel output from 1802 to front panel - useful for debugging and/or high speed data PiZero/1802 exchange in conjunction with switch overrides
<li>Intercepts the –INT signal from  the front panel when PiZero is in control so that front panel interrupts from LED mux circuit don't disrupt downloads before 1802 interrups can be disabled.
<li>Prototype interconnect area with connections for three uncommitted PIZERO gpio pins and the 1802 ef1, ef2, & interrupt pins (plus 5v , 3.3v, & GND)
<li>Jumpers to bypass both the MWR and RUN connections from front panel.
<li>Form factor & connectors to fit into MC stack
<li>WiFi, USB, HDMI, and composite video via PiZero connectors accessible 
<li>PiZero utility written in C to load program code to 1802
<li>Run  A18 for development and loading of code on PiZero
<li>Power both MC and PiZero via single USB wall wart
<li>All-in-one form factor (requires extension ring to fit into Altoids tin)
<li>Works with either front panel type or without any front panel
<li>3.3v to 5v level conversion as needed
</ol>