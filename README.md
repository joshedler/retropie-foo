# retropie-foo

A collection of scripts/enhancements to my [RetroPie](http://blog.petrockblock.com/retropie/)

See the appropriate README under each folder (there's only one at the moment) for more information.

# My RetroPie

0. [Raspberry Pi 2, Model B](https://www.sparkfun.com/products/13297) from SparkFun.
0. [Raspberry Pi 2, Model B enclosure](https://www.sparkfun.com/products/12997) also from SparkFun.
0. [Edimax EW-7811Un 150 Mbps Wireless 11n Nano Size USB Adapter](http://amzn.com/B003MTTJOY)
0. [Kensington Bluetooth 4.0 USB Adapter for Laptops](http://amzn.com/B00B2HVAT0)
    - _I'm not exactly sure if this is the same one I have; I bought the one I have at a Big Box store._
0. [Transcend 16GB Class 10 SDHC Flash Memory Card](http://amzn.com/B003VNKNEQ)
0. 2x [Six-Axis DualShock Wireless Controller for PlayStation 3](http://amzn.com/B00BYGJ99M), one blue and one red
0. [HDE Black Dual Charging Station Compatible with Sony PS3 Controller](http://amzn.com/B00FA5PKDM)
0. 2.5A Micro-USB Power Supply
    - I got this as part of a starter kit that originally contained a Raspberry Pi Model B.
    - It appears that the [amazon.com](http://www.amazon.com/dp/B00DG9D63A/ref=cm_sw_su_dp) link I ordered now has the new Raspberry Pi 2's.

# My challenges

I originally ordered a [wired gaming controller](http://amzn.com/B002B9XB0E) and we quickly got tired of having to sit so close to the TV. I found the PS3 controllers and a Bluetooth adapter and followed the RetroPie instructions to pair them up... The biggest challenge was there were only 2 USB ports on the original RPi, and one was needed to connect each controller via USB and the other was needed for the Bluetooth adapter for pairing, so there was no way to attach a USB keyboard and/or a WiFi adapter and I had to get creative. Enter the new RPi 2, which has 4 USB ports and that's no longer an issue.

The next challenge was the controllers do not always pair on startup for various reasons. It appears that sometimes the Bluetooth driver is not in the right mode. When the controllers do not pair in time, EmulationStation eventually loads and shuts down any further ability to pair, so you're stuck unable to do anything until you either attach a keyboard or SSH into the RPi to reset it and try again.

Enter the rc.local script in the etc/ folder... It attempts to wait for the controller(s) to pair, and will restart the RPi if it detects and invalid state.
