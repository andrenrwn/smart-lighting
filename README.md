# smart-lighting
This repo aims to be a gallery of information about smart lighting, focusing on open-source and DYI-able projects

# my requirements
When I started trying to choose lighting for my home, I looked around the options and focused on the following things that I wanted:

1. Changeable and maintainable.
2. Smart. This means the ability to automate without physical access.
3. It needs to be good enough for general-purpose lighting, not just mood or decorative lighting.
4. It must not have any vendor lock-in features

# options
There are as many lighting vendors and options that could make your head spin, so let's start this exploration from my final choice, and work backwards.

What I ended up choosing:
- Devices based on Zigbee
- Home Assistant Yellow with Zigbee2MQTT
- Downlights, LED strips, LED panels for general lighting

# considerations

# New renovation

# Smart Downlights
In a newly renovated home, you have full freedom to add or change a false ceiling, then add or change the lighting fixtures.  This frees us up from being locked in to specific fixtures and screw types, allowing us to choose any fixture we like.  Gypsum board for false ceilings are also more flexible than I thought they could be.  Holes for fixtures and downlights can be covered back with gypsum and painted over as if they were never there.

If you ever have to deal with choosing lighting mechanism, you know it can get crazy because there are so many plug and screw standards and a multitude of fixtures based on decades of history.
https://www.screwfix.com/guides/electrical-lighting/light-bulb-buying-guide

So why settle for a fixture that someone else chose for you?  When I tried to change my current fluorescent bulbs with LED types, I discovered that I have a PL-C plug.  Finding PL-C LED replacements are more time consuming to find and therefore less flexible.  Plus in most cases, it is always required to remove the existing ballast, which requires a rewire (and a visit from an electrician if you don't fancy something a bit more involving than unplugging and replugging a bulb (Insert how many peoeple does it take to change a light blub joke here)).

https://www.harolux.com/how-to-use-4-pin-led-bulb/

Vendor lock-in is a beast and we all should fight it as consumers.  One of the ways to do that is to look at what contract manufacturers are manufacturing to see if there are any commonly used and popular products that absolutely avoids unecessary unique standards.


# LED Strips
SK6812 RGBW.
5 or 12V.

LED Strips come in various types, but the most commonly used by tech geeks are WS2811 compatible individually addressable RGB LED strips.  The problem with RGB LEDs is that they usually have lower CRI, and is usually only usable as mood lights, not general lighting.  To use 

There are even more flexible RGBCCT types, which comes with 5 different LED channels (R, G, B, cool white, and warm white).  However these types of controllers are rarer, thus rendering our options to be less flexible than RGBW.

The nice thing about SK6812 and WS2811/2812/2814/2815 LED strips are that they are dimmable using discrete PWM from most controllers.

# WLED
If your lighting device is not using Zigbee, then the other option is WLED through Ethernet or Wi-Fi.

There are several different options to get WLED controllers to control LED strips and LED matrices.

## QinLED
[QinLED](https://quinled.info/quinled-dig-octa/) makes components that you can use to build WLED controllers based on ESP32.  It makes it easy for you to reprogram and custom-build to your home's lighting specifications.  The controllers are flexible and has safety fuses, something that is *very* useful when renovating a new home, because low-skilled workers (who are usually the only option we get unless you're a multi-millionaire) will absolutely destroy your LED controllers when building your house for you.  Our electrical workers burned through dozens of these fuses connecting things in the wrong polarity and having badly manufactured LED sheets run solders on the edges causing them to short-circuit.  Fuses are your friend.  Always have them around.

## Gledopto
[Gledopto](https://www.gledopto.com/h-col-420.html) makes ready-built WLED controllers.  These are compact and integrated, but do not have fuses.  If you need to reflash physically, get the model with UART.  My installation of LED sheets burned through at least two Gledopto RGBCCT PWM controllers before I used QinLED to test them first.

# Wiring
To power modern smart lighting, the most flexible cable arrangement is at least one live and one neutral wire. A grounding wire is excellent to have.
Most lighting wiring is only expected to use a lower amount of watts, so adding lighting cables are usually less costly than running socket cables.

The exception here is LED strip and LED panel wiring.  Low voltage LED strips will need more corrent, and therefore will need thicker wires.  I know, small LED strips with low current can still use thin wires, but long runs of dense SK6812 LED strips several meters long (as in the case of most general lighting) can consume a much higher maximum wattage and current.
In most cases these will be compensated by 


# Zigbee

Zigbee is more popular now because of TuYa, a Chinese IoT company that develops smart home devices that are relatively low cost.  A lot of different smart home brands (ie. Kyla, etc) are actually TuYa brands which work with their SmartLife app or LifeSmart app and devices.
Wi-Fi smart IoT devices is also popular becasue of TuYa.  However, TuYa devices are mostly vendor-locked-in by TuYa's smartlife smarthome app in which you have to register your devices to your TuYa cloud account for remote control from your phone.  Many efforts have been made to disconnect TuYa devices from the cloud and ensure the smart control can be local, but ironically software updates (which are also supposed to include security and functionality fixes) seems to defeat these efforts.  TuYa offers contract manufacturers an IoT software development platform and ready-made software which white-label contract manufacturers and OEMs can easily adopt and slap their own brand on, and I think this is one of the reason for its popularity.  Manufacturers have basically outsourced all their software developemnt efforts to TuYa.  Initially TuYa made software that are based on Espressif ESP8286 and ESP32, a Wi-Fi and Bluetooth compatible chipset.  These make it easier for the open-source community to develop custom firmware to replace TuYa's own firmware so the devices work totally locally without any tether to the cloud.  But recently, TuYa developed their own Zigbee and their own ESP32-like microcontroller making efforts to reflash TuYa devices with open-source firmware like Tasmota and ESPHome more difficult.  However, TuYa's ZigBee devices are still built to the ZigBee standard, making Zigbee smart home devices a better choice than Wi-Fi versions because they can work locally in a home with open-source ZigBee coordinators while being isolated from the Internet.

While Matter is on the horizon, the standard is more complicated than Zigbee and many of the DIY implementations are still under construction.  Zigbee devices are already on the market and a lot cheaper and available to purchase now, and they are known to work.

Z-Wave is popular in Europe, so this may be another option you can explore.  However, from my cursory view of the marketplace, there are less Z-Wave options than Zigbee devices.  There may be more Wi-Fi devices now, but we can't use most low-cost off-market Wi-Fi devices because they will most likely be TuYa wi-fi versions.

Other vendor systems:

KNX is a popular standard in Europe.  It has a really long history with wired solutions and its own network stack.  It is too complicated to study and implement for low-skilled workers who will be tasked to wire up my apartment.  The devices required in the system are also a lot more expensive.

Lutron is a time tested brand for home automation. They are sold with their own junction boxes and also have their own communications systems.  The contract installation is expensive, however, and it will also require skilled labor and significant vendor lock-in.  It may be cheaper than installing KNX, but it is much more expensive than buying off-market ZigBee devices.

https://www.customcontrols.co.uk/blog/lutron-lighting-vs-knx-vs-zwaverf/

Control-4 is another offering which requires a vendor installation.  It is not catering for a DIY market, but it is somewhat open-source and I understand it ties in whole-house video and audio very well together.  It might be my choice if I wanted a turnkey solution and didn't want to choose my own devices and integrate them myself.

https://www.c4forums.com/forums/topic/36361-is-c4-getting-lapped-by-open-source-solutions/


# Home Assistant Yellow / Green

Buying the hardware gets you the needed hardware and software integrated right out of the box.  It saves install time and deciding on how to manage an OS and device drivers (like the ZigBee coordinator, Wi-Fi and bluetooth), which would have saved me a lot of time troubleshooting linux and python drivers for ZigBee, Z-Wave and bluetooth using different linux distribution flavors on a Raspberry PI.


# OpenHASP

OpenHASP are firmware replacements for LCD panels that can act as light switch relays or DIY user interfaces.  Imagine a switch that is so flexible that you can program just about any touch-screen user interface on.
Physical ZigBee switches works very well.  There are buttons, dimmers and sliders and dials, but a touchscreen can mimic a very large number of these.




What do you think the simplest and most minimal modern Smart Home system should be when building or renovating a new place?
