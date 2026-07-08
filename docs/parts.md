# Parts and Materials
---
### Previous Page: [README](../README.md)
---

For this part of the guide, I will break down where I got each part, how many were used, and the general purpose of the part. 

List entries will be formatted as follows:

* Store
  * **Qty.** - Item Name/Model Number
    * Explanation

#### Note: 
If you want to build the exact thing I built, buy (almost) everything on this list!

---

## Table of Contents:
* [eBay](#ebay)
* [Amazon](#amazon)
* [Other Suppliers](#others)
* [Tools](#odds-and-ends)
* [Odds and Ends](#odds-and-ends)

---

### eBay
* **2** - [Motorola VRM650](https://www.ebay.com/sch/i.html?_nkw=motorola+F3451A), Model **F3451A** (450-512 MHz)
  * Must be that exact model number, otherwise the radio will be in the 800 MHz range. See [this document](../external/VRMInfo.pdf) for a more in-depth model number list
* **2** - [Motorola HLN6412A Connector](https://www.ebay.com/sch/i.html?_nkw=Motorola+HLN6412A) (Optional)
  * Only required if you want the official connector for this radio, but is pricy and hard to find. I will explain how to use a normal DB25 in [Wiring](./wiring.md).

---

### Amazon
* **Required Radio Parts**
  * **1** - [MaxtonData RLN4008B RIB](https://www.amazon.com/dp/B0F5LFQNLM/)
    * This is __required__ for programming the VRM650/VRM850/MCS2000. RIB-less cables have a low success rate, and do not exist for the VRM series. Alternative RIBs are available for cheaper from other sellers, but this is the one I used and works well for me.
  * **1** - [USB to RS232 Cable](https://www.amazon.com/dp/B006AA04K0/)
    * I used an old Plugable PL2303-based cable, but FTDI-based cables are recommended for reliability, especially on Windows 11. The serial port created by this cable will be passed through to a Windows XP VM, which will be explained in [Configuration](./config.md).
  * **1** - [9V DC Power Supply](https://www.amazon.com/dp/B077XPLH92/) (Optional)
    * This eliminates the need for a 9V battery in the RIB, and feels safer than possibly having a battery die during a program write. 
    * Make sure that the connector is center positive if you use a different supply!
  * **2** - [2-pin SAE Power Cables](https://www.amazon.com/dp/B0DNCM9D2T/)
    * I personally used a different cable from the store I work at, but this is an easier option with a built-in fuse holder. Note the polarity on other cables, the red wire should be on the insulated side of the connector.
    * If using the fuse holder listed later, I would recommend cutting off the built-in fuse holder and crimping new rings.
  * **4** - [DB25 Female Connectors](https://www.amazon.com/dp/B0841FCNJ9/) (Pack of 6)
    * The required quantity changes if the HLN6412A connectors are used. If not using the HLN6412A, 2 connectors will be required to build the Y-cable to connect the MMDVM to the radios.
    * 2 connectors will be required no matter what to build the RIB-to-radio cable.
  * **1** - [DB9 Male Connector](https://www.amazon.com/dp/B09BZ4YZ9R) (Pack of 18(!))
    * Only needed if using the [Repeater Builder STM32_DVM](#others)
  * **~2 ft** - [24 AWG 6P Ribbon Cable](https://www.amazon.com/dp/B099W8RD5K/) (Roll of 5 ft)
    * Only needed if using the [Repeater Builder STM32_DVM](#others). Used for the cables from the MMDVM to the radios.


* **Optional Chasis Parts**
  * **1** - [2U Server PC Case](https://www.amazon.com/dp/B0D41ZJH3D/)
    * This thing is made out of *absolute crap*, but that means it's perfect for chopping up into a repeater housing. "Modifications" required can be found in the [Assembly](./assy.md) page.
  * **1** - [Very Cheap PC Power Supply](https://www.amazon.com/dp/B08FLVGVHN/)
    * This one is a bit strange, I just used this to harvest the rear panel as a filler. I saved the rear panel itself, C14 socket, power switch, and cooling fan. Required PSU butchering can be found in the [Assembly](./assy.md) page.
    * This part could (and should) also be omitted with a 3D printed panel, with features for the C14 socket, switch, and RJ45 panel mount included. 
  * **1** - [Compact 12V Power Supply](https://www.amazon.com/dp/B07WHJF1Q8/)
    * I have not had a chance to test for RFI yet, but this is an actual MEANWELL switching supply, and has good reviews for amateur radio use. 
  * **1** - [6 Position Fuse Holder with Power Rails](https://www.amazon.com/dp/B0838TZ2Z2/)
    * This is how I would recommend everything be connected to power. Everything is protected by a fuse, and power wiring is simplified to a common connection point.
  * **2** - [Type N Panel Mount Connectors](https://www.amazon.com/dp/B09GFMVK2R/) (Pack of 2)
    * These are installed into the I/O shield filler to pass-through the antenna connectors for the RX and TX radios. 
  * **1** - [Type N 90 Degree Adapter](https://www.amazon.com/dp/B07V8MY7SG) (Pack of 2)
    * Used to make clearance for the TX radio later on.
  * **2** - [Type N to Mini UHF Jumper Cable](https://www.amazon.com/dp/B07VDYX6PV/)
    * Required to connect the VRMs to the Type N panel mounts.
  * **2** - [Type N to SO-239](https://www.amazon.com/dp/B083WDV529/) (Pack of 2)
    * Only needed if using PL-259 cables to connect to the repeater.
  * **1** - [PWM Fan Controller with Temp Sensor](https://www.amazon.com/dp/B0GWV4XNXY/) (Pack of 2)
    * Used to automatically ramp up the 80mm fans included with the enclosure when the TX radio warms up.


* **Optional Pi Chassis Parts**
  * **1** - [12V to 5V 5A USB-C Voltage Regulator](https://www.amazon.com/dp/B0CRVW7N2J/)
    * Used for powering the Pi from the 12V power supply.
  * **1** - [USB 3.0 Internal Header to USB A](https://www.amazon.com/dp/B0719J5M9V/)
    * This is only required if you want to pass the front panel USBs to the Raspberry Pi.
  * **1** - [USB-C 90 Degree Adapter](https://www.amazon.com/dp/B0CNGFZ1JD/) (Pack of 2)
    * Required for Pi power connector due to mounting clearance issues.
  * **1** - [Panel Mount RJ45](https://www.amazon.com/dp/B0CFVYJMT2/) (Pack of 2)
    * Required to make the ethernet port accessible on the Pi. I had WiFi reliability issues inside the enclosure.
  * **1** - [1ft SlimRun CAT6A Patch Cable](https://www.amazon.com/dp/B07958SQKS/) (Pack of 5)
    * Connects the panel mount RJ45 to the Pi.

---

## Others
* Raspberry Pi 
  * As everyone knows, electronic prices are insane right now, especially including the Raspberry Pi. I would not recommend anything over the Pi 4, as the Pi 5 is absolute overkill for Pi-Star and would just generate more heat.
  * My recommendations (RAM sizes listed):

    | [Pi 3](https://rpilocator.com/?country=US&cat=PI3) | [Pi 4](https://rpilocator.com/?country=US&cat=PI4) | [Pi Zero](https://rpilocator.com/?country=US&cat=PIZERO2)* |
    |---|---|---|
    | B+ (1 GB)| 1 GB | 2 W |
    | A+ (512 MB) | 2 GB | |

    *The Pi Zero (1st Gen) will not work with newer releases of WPSD and is generally too slow for what is needed. A Pi Zero 2 W is required if using a Zero.
  * The table headers link to rpilocator, which aggrigates stock and prices for different vendors. Click whichever model you're interested in to see stock and prices.

* MMDVM
  * Really only 2 good options exist for repeaters:
    * [Repeater Buildser STM32_DVM](https://www.repeater-builder.com/products/stm32-dvm.html) - $95 + S&H (at time of writing)
    * [ZUM Radio MMDVM-Pi](https://zumradio.com/products.html#mmdvm-pi) - $99.95 + S&H (at time of writing)
  * Personally, I have had *terrible* luck with the MMDVM-Pi and would certainly recommend the STM32_DVM. I used the MMDVM-Pi for my build as I had a semi-broken one left over from another repeater, but prefer working with the STM32_DVM from my experience. This guide will go over setup of both MMDVM options to the best of my ability.

---
## 3D Printed Parts

* **1** - [I/O Shield Filler](../3d-files/IO%20Panel/IOPanel.stl)
  * This is needed to fill the hole where the I/O shield would be on a PC motherboard. The filler has mounting holes for the 2 panel mount Type N connectors.
  * Please excuse the poor 3D model quality, I still am very inexperienced with FreeCAD.



---

## Odds and Ends

These are the random bits and bobs that I used throughout this project.
* Tools:
  * Drill
  * Screwdriver Kit
  * Step Drill Bit
  * Drill Bit Index
  * Vice-grips (for pulling standoffs, see [Assembly](./assy.md))
  * Soldering Iron
  * Die Grinder (for butchering PSU, see [Assembly](./assy.md). Can also be done with tin snips.)
  * Multimeter
* Hardware:
  * **6** - M4 x 6mm Cap Head Screws (I/O Panel)
  * **4** - M4 x 10mm Cap Head Screws (Power Supply)
  * **4** - M4 x 18mm Cap Head Screws (Fuse Block)
  * **10** - M4 Nuts
  * **14** - M4 Flat Washers
  * **8** - M3 x 8mm FLat Head Hex Screws (Type N Panel Mounts)
  * **8** - M3 Washers 
  * **8** - M3 Nuts
  * **1** - Roll of 1/2" 3M Vehicle Trim Tape (Mounting Radios and 5V Regulator)
  * **A bunch** - Small Zip Ties (Cable Management)
* Electrical:
  * **4** - 12-10 AWG #10 Ring Terminals (Radio Power Cables)
  * **3** - 14-16 AWG #10 Ring Terminals (AC Input Cables)
  * **4** - 22-18 AWG #10 Ring Terminals (5V Regulator and 120mm Fan)
  * **2** - Red 15/30/45A Powerpole Housings (AC Input Cable)
  * **2** - Black 15/30/45A Powerpole Housings (AC Input Cable)
  * **2** - Green 15/30/45A Powerpole Housings (AC Input Cable)
  * **6** - 15A Powerpole Pins (AC Input Cable)
  * **~2 ft** - 16 AWG Black Silicone Wire (AC Input Cable)
  * **~2 ft** - 16 AWG White Silicone Wire (AC Input Cable)
  * **~2 ft** - 16 AWG Green Silicone Wire (AC Input Cable)
  * Solder
  * Asstorted heat shrink for all wires and ring terminals.

---
### Next Page: [Assembly](./assy.md)
---
