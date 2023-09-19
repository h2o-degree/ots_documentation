
# H2O Degree OTS Documentation

## L54120
[Port 210/211](#210)  
[Port 212/213](#212)  
[Port 52](#52)  
    [Hardware Diagnostic Byte Bitmap](#52.1)  
    [Water Diagnostic Byte Bitmap](#52.2)  
    [Status Byte Bitmap](#52.3)  

##  L542xx
[Port 140/141/145](#14x)  
[Port 51](#51)  

<a name="210"/>  

# L54120 Port 210/211 Aqura Point of Use Water Meter Commodity Packet  
For firmware version < 0.6 with born on date earlier than Oct 13th 2022  
Lora Port : 210 - Hourly , network setting ping or power up transmission  
LoRa Port: 211 - Magnet triggered transmission  

| Byte Index | Descriptipn | Data Type | Bitmap / Notes |
| --- | --- | --- | --- |
| 0 | Water gallons integer | 32-bit big endian unsigned int | |
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | Water gallons decimal | 8 bit big endian dec | value / 256 | 
| 5 | Flow events | 16-bit big endian unsigned int | |
| 6 | | | |
| 7 | Flow time minutes | 16-bit big endian unsigned int  | 
| 8 | | | |
| 9 | Transmit attempt count | 16-bit big endian unsigned int | 
| 10 | | | |

<a name="212"/>  

# L54120 Port 212/213 Aqura Point of Use Water Meter Commodity Packet
For firmware version >= 0.6 with born on date later than Oct 13th 2022
Lora Port : 212 - Hourly , network setting ping or power up transmission
LoRa Port: 213 - Magnet triggered transmission


| Byte Index | Descriptipn | Data Type | Bitmap / Notes |
| --- | --- | --- | --- |
| 0 | Water gallons integer | 32-bit big endian unsigned int | |
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | Water gallons decimal | 8 bit dec | value / 256 | 
| 5 | Flow events | 16-bit big endian unsigned int | |
| 6 | | | |
| 7 | Flow time minutes | 16-bit big endian unsigned int  | 
| 8 | | | |
| 9 | Battery VDC millivolts | 16-bit big endian unsigned int | 
| 10 | | | |

<a name="52"/> 

# L54120 Port 52 Aqura Point of Use Water Meter Heath Packet

Lora Port : 52 - Once every 23 transmissions


| Byte Index | Descriptipn | Data Type | Bitmap / Notes |
| --- | --- | --- | --- |
| 0 | Hardware diagnostic | 8-bit bitmap | see table 52.1 |
| 1 | Water diagnostic | 8-bit bitmap | see table 52.2 |
| 2 | Temperature fahrenheit | 8-bit big endian unsigned int | |
| 3 | Reset code |  8-bit big endian unsigned int  | |
| 4 | Battery voltage | 16-bit big endian unsigned int | (value +200)/100 | 
| 5 | | | |
| 6 | Status byte | 8-bit bitmap | see table 52.3 |
| 7 | Reset count | 16-bit big endian unsigned int  | 
| 8 | | | |
| 9 | Transmit attempt count | 16-bit big endian unsigned int | 
| 10 | | | |

<a name="52.1"/> 

## Table 52.1 : L54120 Hardware Diagnostic Byte Bitmap

| Bit | Descriptipn |
| --- | --- |
| 0 | 1 if Main Baby Board Missing, 0 if Main Baby Board is detected.|
| 1 | Undefined|
| 2 | 1 if Didn't receive NetworkKey during Join Process|
| 3 | 1 if the WaterMeter is in Aggressive Tx mode|
| 4 | 1 if Second Baby Board Missing, 0 if Second Baby Board is detected.|
| 5 | Deep Sleep Enabled (1 : Enabled via Write packet from production, 0 : disabled )|
| 6 | Undefined | 
| 7 | Undefined | 

<a name="52.2"/> 

## Table 52.2 : L54120  Water Diagnostic Byte Bitmap

| Bit | Descriptipn |
| --- | --- |
| 0 | 1 if there is no flow for 30 days, 0 when flow is detected. |
| 1 | undefined |
| 2 | undefined |
| 3 | 1 if continuous flow for 5 hours. 0 when continuous flow is stopped |
| 4 | 1 if continuous intermittent flow for 24 hours. 0 when when cont. int. flow is stopped |
| 5 | 1 after detecting a low flow for 1 hour. 0 when low flow is stopped |
| 6 | Undefined |
| 7 | Undefined |

## Table 52.3 : L54120 Status Byte Bitmap

<a name="52.3"/> 

| Bit | Descriptipn |
| --- | --- |
| 7 MSB |  Magnet Flag 1 = magnet generated packet,  0 = not a magnet generated packet |
| 6,5,4 | Major firmware number |
| 3,2,1 | Minor firmware number |
| 0 |  Power up packet flag 1 = power up | 0 = not power up |

<a name="14x"/> 

# L542xx Port 14x Series Dry Contact Pulse Meter Commodity Packet

Lora Port : 140 - Hourly , network setting ping or power up
LoRa Port: 141/145 - Magnet triggered transmission

| Byte Index | Descriptipn | Data Type | Bitmap / Notes |
| --- | --- | --- | --- |
| 0 | Channel 1 pulse count | 32-bit big endian unsigned int | |
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | Channel 2 pulse count | 32-bit big endian unsigned int | value / 256 | 
| 5 | | | |
| 6 | | | |
| 7 | | | | 
| 8 | Battery voltage | 8-bit big endian unsigned integer | (value +200)/100 |
| 9 | Transmit attempt count | 16-bit big endian unsigned int | 
| 10 | | | |

<a name="51"/> 

# L542xx Port 51 Series Dry Contact Pulse Meter Heath Packet

Lora Port : 51 - Once every 23 transmissions

| Byte Index | Descriptipn | Data Type | Bitmap / Notes |
| --- | --- | --- | --- |
| 0 | Reserved | 8-bit | not used |
| 1 | Reserved | 8-bit | not used |
| 2 | Microchip mac staatus flags | 32-bit big endian bitmap |  Stack dependent. See table 51.1 |
| 3 | | | |
| 4 | | | | 
| 5 | | | |
| 6 | Status byte  | 8-bit bitmap | |
| 7 | Reset count |  16-bit big endian unsigned int  | |
| 8 | | | |
| 9 | Transmit attempt count | 16-bit big endian unsigned int | 
| 10 | | | |

## Table 51.1 : L54230 Status Byte Bitmap

Stack document: https://ww1.microchip.com/downloads/en/DeviceDoc/40001784B.pdf

| Bit | Descriptipn |
| --- | --- |
| 7 MSB |  Unused  |
| 6,5,4 | Major firmware version |
| 3,2,1 | Stack version - if 5(b101) → v1.0.5 of the Microchip Stack, if 3(b011) → v1.0.3 of the Microchip Stack |
| 0 |  Unused |



