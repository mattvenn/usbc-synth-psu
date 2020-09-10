# USBC Synth PSU

* uses STUSB4500 to negotiate 12v or 15v from a USBC power bank
* uses 4 [DC/DC switchers](https://www.ti.com/product/TPS56339) to supply 12, 9, 5 and 3v outputs for my various synths
* resistors can be changed to set different output voltage
* JP1 can be bridged and 12v DC/DC components not placed if power bank can supply 12v.

![board](board.png)

[PDF schematic](schematic.pdf)

[gerbers](synth-psu-2020-09-01-fab.zip)

[bom](synth-psu-bom.csv)

# functional todo

* looks like aukey charger only goes up to 12v, so add a jumper to short out one of the DC switchers - done
* check noise with a 3v generated supply into PO - done

# schematic todo

* add part numbers

* enable switchers only if PD is good? - no, as PD is open drain and would need an inverter, plus DCDC float to enable
* check max input dc/dc - 5v! need to find another - how about https://www.ti.com/product/TPS56339#product-details##pps - done
* calculate all R1 & R2 for dc/dc - done, used TI webench
* calculate all LED R  - done
* add more psu outputs (or can remove the 12v one?) - done
* do we need 5v? (aukey can do 2x usb 5v as well as PD on usbC) - done anyway
* mosfet and check pinout - done
* double check pinout and wiring of usb chip - done

# pcb todo

* check gerbers against other designs for pinout

* check space for molex header - done
* mount holes fit 20mm grid - done

# psu design

## test

FFT of PO-12 with DC/DC 3.3v supply 

![fft audio noise](docs/dcdc-po-out.png)

# programming

The NVM of the STUSB4500 needs to be programmed to sink more than the highest output you want. 
For example 15v (for 12v DC/DC converter).

The Aukey USBC powerbank I bought can only supply up to 12v, so I set the number of PDOs to be 2, and 
ask for 12v. Then I bridge JP1 and don't place any of the DC/DC for the 12v supply.

Here is the [Sparkfun demo firmware I used](firmware/src/program.ino). To do the programming I used platformio with an Arduino Uno.

Connect the I2C pins and ground to header J1 on the pcb. *SDA and SCL will both need pullups.*

To build and upload, run:

    pio run --target upload

Then open the serial port to see the results.

# order

* psu power plugs (volca)
* molex 2 pin header and housing, check crimp supply
* how to connect PO - solder on a header directly
* standoffs

# notes

* proposed USBC charger: https://www.amazon.es/AUKEY-10000-mAh-Delivery-3-0-Cargador-Port%C3%A1til/dp/B07B4RQ47B/ref=sr_1_4?ascsubtag=UUacUdUnU67894YYwYg&dchild=1&keywords=AUKEY+USB+C+Power+Bank+10000mAh%2C+PD+Power+Bank+Slimline+with+18W+PD&linkCode=gs3&qid=1598631552&sr=8-4&tag=androcentr0f-21
* STUSB4500 datasheet https://www.st.com/en/interfaces-and-transceivers/stusb4500.html
* sparkfun USB PD product https://www.sparkfun.com/products/15801
* tindie USB PD product: https://github.com/oxplot/fabpide2
* sparkfun how to use their PD board: https://learn.sparkfun.com/tutorials/power-delivery-board---usb-c-qwiic-hookup-guide?_ga=2.100271642.500100063.1599656815-1406600584.1576753580
