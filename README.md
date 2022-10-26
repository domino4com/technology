<img align=right src="assets/Example%20xChip.png" width="600">

# Technology
Domino4 is a rapid electronics development solution for developing, making products and learning. Without soldering, wiring, breadboarding, or hardware knowledge, the user can assemble a circuit in a matter of minutes, and get straight to coding. This section covers Technical Specifications. 

**1\. xChip Layout**

Each xChip are a multiple of 32x32 mm.

**1.1 xBus**

xChips have a xBus connection space for each 32mm side, unless component size limits space for the connector on some sides. 

| Top Side Pin | Name | Type | Description |     | Bottom Side Pin | Name | Type | Description |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1   | SCL | Signal | I<sup>2</sup>C |     | 6   | Reset | Signal | Reset |
| 2   | SDA | Signal | I<sup>2</sup>C |     | 7   | Prog | Signal | Programming Pin |
| 3   | GND | Power | Ground |     | 8   | RX/TX | Signal | Serial Receive/Transmit |
| 4   | Vcc | Power | 3.3 volt |     | 9   | TX/RX | Signal | Serial Transmit/Receive |
| 5   | Vsrc | Power | Power from original power source |     | 10  | IO | Signal | GPIO |

**2\. Configuration**

**2.1 I2C Protocol**

Domino4's mission is to simplify building electronic devices. We have chosen I2C as the only communication protocol between xChips. In doing so we have eliminating the need to understand the pins and wiring in general.

**2.2 SPI**

SPI is only available via the 1mm Extension slot on (currently) the extended core (CWV)

**2.3 Serial (also known as UART or RS232C)**

Even though Serial is found on the xBus, we mainly use it for simple programming. Some other xChips, such as the INA (GNSS (GPS)) xChip might also use it. In that case the xChip has to be removed before programming.

**2.3 IO - General-purpose input/output**

Thi spin is connected to the Core like this
| Core | ChipSet | IO Name | Physical Pin | Functionality |
| --- | --- | --- | --- | --- | 
| CWA - Standard Core | ESP32-WROOM-32 | GPIO2 | 24 | Touch2 RTC12 ADC2_2 |
| CWV - Extended Core | ESP32-WROOM-32 | nc | nc | n/a |
| CWB - Battery Core | ESP32-C3 | GPIO0 | 4 | ADC1_0 |
