# Qinled builds

This documents the materials I needed to build my own QinLED controller builds.


## Fans

Brushless cooling fans. 4cm to be built on the box itself.  Can be controlled by PWM or just the relay switch from QinLED's brainboard.
https://www.aliexpress.com/item/1005006011504154.html
https://www.aliexpress.com/store/5038011
https://www.aliexpress.com/item/1005004599877502.html



## Openhasp panels

Guition.  I didn't have good experience with these.  The 5V power supply that comes with the relay part seems to be rather flaky when reflashed with OpenHASP, causing the display to suddenly reboot or become offline after a while. But if you can use a better 5V power supply, these are the cheapest ESP32 smart display panels out there.
https://www.aliexpress.com/item/1005006622746590.html?spm=a2g0o.order_list.order_list_main.126.581d1802U0knWE

Panlee.  These come in different models, but the ones sold in Aliexpress is similar to Guition.  They are more expensive, but they seem to run well.
https://www.aliexpress.com/item/1005005188547984.html?spm=a2g0o.order_list.order_list_main.108.581d1802U0knWE

I recommend to go directly to Alibaba using OpenHasp's compatible devices list recommendation.
These are two solid choices that I have used:
https://www.openhasp.com/0.7.0/hardware/golden-security/gs-t3e/
https://www.openhasp.com/0.7.0/hardware/lanbon/lanbon-l8/

## Heat shrinkable tubing and heat gun (you can use a hairdryer)

https://www.aliexpress.com/item/1005006704702575.html

## Wire soldering tool

https://www.aliexpress.com/item/1005006965592358.html

## Fuses
https://www.aliexpress.com/item/1005005825809084.html

## Crimp terminals
https://www.aliexpress.com/item/1005007705089635.html


## 3-pin wire connectors

These are the *best* ones I have used so far.  They are unpluggable, making it easy to test LED strips by just connecting these onto different sources and destinations.  It saves a lot of time screwing and unscrewing wires to LED drivers and strips.
https://www.aliexpress.com/item/1005006887848609.html
https://www.aliexpress.com/store/1103367264

## Junction boxes

These come with different sizes that fit a Meanwell power supply.  I used 300x200x180mm (fits one power supply, 2 DIG-QUAD power boards and 2 brainboards) to 300x200x130mm (Which fits one of each)
https://www.aliexpress.com/item/1005005509502688.html
https://www.aliexpress.com/item/1005005788040245.html

## Small USB pluggable vacuum cleaner

Something to such in all the plastic shavings from the junction box when drilling holes through them and from acryllic sheets if you're building platforms for the brainboards
https://www.aliexpress.com/item/1005005823479991.html


## Waterproof SK 6812 LEDs in milky white for wet areas
https://www.aliexpress.com/item/4000554999821.html

## Gledopto store for WLED controllers
https://gledopto.aliexpress.com/store/3685003?spm=a2g0o.order_list.order_list_main.285.581d1802U0knWE

## Meanwell power supplies

I used the LRS series for best watt/price ratio
https://meanwell.aliexpress.com/store/5429250

## JST/XH crimping tools

These are used to make connectors to LED sheets and LED strips
https://www.aliexpress.com/item/4000073000826.html
https://www.aliexpress.com/item/1005001500557953.html

### XH connector kit
https://www.aliexpress.com/item/1005006126531415.html
https://www.aliexpress.com/item/1005005916645484.html


## Ferrule kits (and hex crimper)
https://www.aliexpress.com/item/1005006283631892.html

## plastic nylon washers
https://www.aliexpress.com/item/1005005747262698.html

## Wires

Note that a lot of these are 18AWG wire which is probably good up to 7.5 amps.  Consider the amps you need per strip.  I would choose something thicker, like 16AWG to 12AWG if it was a long strip.
https://www.aliexpress.com/store/911772752
https://www.aliexpress.com/item/1005002571762503.html

## USB Serial adapters to program ESP32 (ie. in Lanbon switches)
https://www.aliexpress.com/item/1005006431762743.html

## Hammer-in solderless LED strip connectors
https://www.aliexpress.com/item/1005005515646653.html

## M3 hex screw nut kit (and M2.5) (M4 is also useful)
https://www.aliexpress.com/item/1005007498157463.html
