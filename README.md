# USBC Synth PSU

* uses STUSB4500 to negotiate 12v or 15v from a USBC power bank
* uses 4 [DC/DC switchers](https://www.ti.com/product/TPS56339) to supply 12, 9, 5 and 3v outputs for my various synths
* resistors can be changed to set different output voltage
* JP1 can be bridged and 12v DC/DC components not placed if power bank can supply 12v.

![board](board.png)

[PDF schematic](schematic.pdf)

[gerbers](synth-psu-2020-09-01-fab.zip)

[bom](synth-psu-bom.csv)

# Project log

For build notes, problems and fixes, please check the [project log](docs/log.md)

# Errata

* hole size is 5.3mm, should be 6 for M5 - fixed in PCB, not in gerbers

# Resources

* proposed USBC charger: https://www.amazon.es/AUKEY-10000-mAh-Delivery-3-0-Cargador-Port%C3%A1til/dp/B07B4RQ47B/ref=sr_1_4?ascsubtag=UUacUdUnU67894YYwYg&dchild=1&keywords=AUKEY+USB+C+Power+Bank+10000mAh%2C+PD+Power+Bank+Slimline+with+18W+PD&linkCode=gs3&qid=1598631552&sr=8-4&tag=androcentr0f-21
* STUSB4500 datasheet https://www.st.com/en/interfaces-and-transceivers/stusb4500.html
* sparkfun USB PD product https://www.sparkfun.com/products/15801
* tindie USB PD product: https://github.com/oxplot/fabpide2
* sparkfun how to use their PD board: https://learn.sparkfun.com/tutorials/power-delivery-board---usb-c-qwiic-hookup-guide?_ga=2.100271642.500100063.1599656815-1406600584.1576753580
