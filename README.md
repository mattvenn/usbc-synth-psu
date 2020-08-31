# functional todo

* check noise with a 3v generated supply into PO
* looks like aukey charger only goes up to 12v, so add a jumper to short out one of the DC switchers

# schematic todo

* check max input dc/dc - 5v! need to find another
* check 
* mosfet and check pinout
* double check pinout and wiring of usb chip
* calculate all R1 & R2 for dc/dc
* calculate all LED R 
* add more psu outputs
* do we need 5v?
* add part numbers

# pcb todo

* check gerbers against other designs for pinout
* check space for molex header
* mount holes fit 20mm grid - done

# order

* psu power plugs (volca)
* molex 2 pin header and housing, check crimp supply
* how to connect PO
* standoffs

# notes

* proposed USBC charger: https://www.amazon.es/AUKEY-10000-mAh-Delivery-3-0-Cargador-Port%C3%A1til/dp/B07B4RQ47B/ref=sr_1_4?ascsubtag=UUacUdUnU67894YYwYg&dchild=1&keywords=AUKEY+USB+C+Power+Bank+10000mAh%2C+PD+Power+Bank+Slimline+with+18W+PD&linkCode=gs3&qid=1598631552&sr=8-4&tag=androcentr0f-21
* datasheet https://www.st.com/en/interfaces-and-transceivers/stusb4500.html
* sparkfun product https://www.sparkfun.com/products/15801
* tindie product: https://github.com/oxplot/fabpide2
