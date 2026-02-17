# TFPX-201 Test Stand Setup

This SOP describes the process to setup the test stand PC. Many of the steps are simply to follow guides already compiled online. Links or PDFs are provided.

## Required Materials

### PC Acessories

- PC
- USB Drive (≥16 GB)
- Keyboard
- Mouse
- Cat8 Ethernet Cable

### FC7 Acessories

- Cat6 Ethernet Cable
- [Ethernet-to-USB Adapter](https://www.digikey.com/en/products/detail/sanoxy/SANOXY-USB3-GIGETH/15780451)
- [SPF Key](https://www.fs.com/products/11773.html)
- [microSDXC Card](https://www.amazon.com/Samsung-Endurance-microSDXC-Monitoring-MB-MJ64KA/dp/B0B1HZLJB1/ref=sr_1_6?crid=1XFP7Z0MG2EHS&dib=eyJ2IjoiMSJ9.9FJOZ73hKCyfLtcwhA2WQhOfo3X30QUTbYFzYf4FaLD_XHy-3_iuk3MdQuofLfxxqbGYyXJyuQ7w-ehR2FKh9WobYcbUr7aWA-AAF1rcQKuJT5_Bm6WonXTKLsjnJ_XAMdGrf8ywazJ0HOs2siVXaVjddGxWo6AJsxwM5LAq8oOYC4rKQLILIlk-xpRnirkmvxN8Q8rJlDq7R_o6CKnCxcmu8Hoa1m5-62bq8hTRKeM.Mlg8IvtfhWiOsEqsHK28OVNp_aO7Wvdc9209XpBF3vA&dib_tag=se&keywords=samsung%2Bpro%2Bendurance%2Bmicro%2Bsd%2Bcard&qid=1729629006&sprefix=samsung%2Bproend%2Caps%2C103&sr=8-6&th=1)
- MicroSD-to-USB Adapter OR MicroSD-to-USB Adapter AND SD-to-USB Adapter

### Low Voltage Acessories

- [Serial RS-232-to-USB Adapter](https://www.amazon.com/gp/product/B00AHYJWWG)
- 4-Pin Male Mini-Fit Molex to 4 Male Banana Plugs
  - Soldered here at BU, made from [2240951044](https://www.digikey.com/en/products/detail/molex/2240951044/21292168), [CT2002-0](https://www.digikey.com/en/products/detail/cal-test-electronics/CT2002-0/5398763), and [CT2002-2](https://www.digikey.com/en/products/detail/cal-test-electronics/CT2002-2/5398764). The top two pins on the molex connector should be soldered to red banana plugs, while the bottom two pins should be soldered to black. See picture below: <br>
<img src="TFPX-201-materials/molex_to_banana.png" width="300" alt="Foo diagram"> <br>

### High Voltage Acessories

- [Female BNC to Dual Male Banana Plug Splitter](https://www.amazon.com/dp/B00VG5HWH2?th=1)
- [Male BNC to Male MCX Right-Angled Cable](https://www.amazon.com/dp/B015ASQBPY)
- Male USB-to-USB Cable

### Coldbox Acessories

- [Flowmeter](https://www.mcmaster.com/catalog/131/640/2968K204)
- 2 [Push-to-Connect Tube Fittings](https://www.mcmaster.com/catalog/131/227/5779K108)
- MicroUSB-to-USB Cable

### ADC Board Acessories

- USB-to-Micro USB cable

### Step 1: Install Software

Follow [```Install_Software.pdf```](./TFPX-201-materials/Install_Software.pdf) to install AlmaLinux9 and needed software to run Ph2_ACF_GUI. Some specific instructions/addendums for our setup are below:

1. Use Rufus to create the boot drive for AlmaLinux if you're using a Windows PC.

### Step 2: Setup FC7

Follow pages 1 to 10 in [```FC7_Setup.pdf```](./TFPX-201-materials/FC7_Setup.pdf) to connect the FC7 to the test stand PC. Some specific instructions/addendums for our setup are below:

1. Our FC7's MAC address is ```08:00:30:00:29:73``` . You don't need to use Wireshark to find it.
2. We only have one FC7, so we call the FC7 ```fc7``` (as opposed to ```fc7-1```) in our test stand PC.
3. For some steps, there are different instructions for diffrent operating systems.Since our test stand PC runs AlmaLinux9, be sure you're running the commands intended for AlmaLinux9.
4. Ignore any instructions that are specific to ```Ph2_ACF``` ; we will be running ```Ph2_ACF_GUI``` .
5. You will need to plug a mini-HDMI into the FMC card's first port and thread the other end through the hold in the side of the cold box.

### Step 3: Setup Keithley 2470

1. Plug the power cable into the wall and the Keithley 2470
2. Connect the Keithley to the PC using a USB-B-to-USB-A cable. The USB-B connects to the Keithley.
3. Connect the banana plug splitter to BNC connector into the Keithley's FORCE HI and FORCE LO terminals on the front of the Keithley. Make sure the ground ("GND") tab on the side of splitter is pointing down.
4. Connect the BNC-to-MCX connector to the female BNC on the banana splitter. Thread the cable through the hole in the side of the coldbox.

### Step 4: Setup Keysight E3633A

1. Plug the power cable into the wall and the KeysightE3633A
2. Connect the Keysight to the PC using the RS232-to-USB cable.
3. Plug in the 4 male banana plugs that lead to the 4-pin Molex into the front terminals of the Keysight. The plugs are color-coded with the terminals, and the terminals of like color are connected with metal bridges, so it does not matter which red/black banana plug connects to either red/black terminal. Thread the 4-pin Molex connector through the hole in the side of the coldbox.

### Step 5: Setup Coldbox Electronics Box

1. Plug the coldbox power cable into the wall. The coldbox power cable is built in to the coldbox. There's also no ON/OFF switch, so plugging/unplugging the coldbox is how one turns it on/off.
2. Connect the built-in RS232 connector to a RS232-to-USB adapter. Plug the USB into the PC.

### Step 6: Setup ADC Board

1. Connect the USB end of a USB-to-micro USB cable to the PC. Thread the micro USB end through the hole in the coldbox.

### Step 7: Install ```Ph2_ACF_GUI```

1. Follow the instructions on the [Ph2_ACF_GUI Getting Started page](https://github.com/OSU-CMS/Ph2_ACF_GUI/wiki/Getting-Started).
