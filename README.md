# Technology
Domino4 is a rapid electronics development solution for developing, making products and learning. Without soldering, wiring, breadboarding, or hardware knowledge, the user can assemble a circuit in a matter of minutes, and get straight to coding. This section covers Technical Specifications. 

**1\. xChip Layout**

Each xChip are a multiple of 32x32 mm.

![xChip Layout](assets/Example-xChip.png)

**1.1 xBus**

xChips have a xBus connection space for each 2U side, unless component size limits space for the connector on some sides. In the above picture of the RL02 (LoRa xChip), the North connector is occupied by a SMA connector, in this case to connect an antenna to the xChip.

| Top Side Pin | Name | Type | Description |     | Bottom Side Pin | Name | Type | Description |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1   | SCL | Signal | I2C |     | 6   | Reset | Signal | Reset |
| 2   | SDA | Signal | I2C |     | 7   | Prog | Signal | Programming Pin |
| 3   | GND | Power | Ground |     | 8   | RX/TX | Signal | UART Receive/Transmit |
| 4   | Vcc | Power | 3.3 volt |     | 9   | TX/RX | Signal | UART Transmit/Receive |
| 5   | Vsrc | Power | Power from original power source |     | 10  | IO | Signal | GPIO |

**2\. Configuration**

Some of the xChips have alternative configuration options, which is only needed in very seldom cases. The two most typical cases is I2C address selection and UART RX/Tx direction. In all cases of I2C address selection and with exception of a few cases in UART Rx/Tx direction setting, the configuration is done by closing or opening a pair of solder pads. In this case you obviously need a solder iron, but is only in seldom cases and for that reason we chose this method rather than an elaborate method using switches.

**2.1 I2C Protocol**

Domino4's mission is to simplify building electronic devices. We have chosen I2C as the only communication protocol between xChips. In doing so we have eliminating the need to understand the pins and wiring in general.

**2.2 SPI**

SPI is only available via the 1mm Extension slot on (currently) the extended core (CWV)

**2.3 UART (also known as Serial or RS232C)**

Even though UART is found on the xBus, we mainly use it for simple programming. Some other xChips, such as the INA (GNSS (GPS)) xChip might also use it. In that case the xChip has to be removed before programming.
