

# L54120 Port 210/211 Aqura Point of Use Water Meter Commodity Packet  
For firmware version < 0.6 with born on date earlier than Oct 13th 2022  
Lora Port : 210 - Hourly , network setting ping or power up transmission  
LoRa Port: 211 - Magnet triggered transmission  

| Byte Index | Descriptipn | Data Type | BItmap / Notes |
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
| 9 | Transmit attempt count | 16-bit big endian unsigned int | 
| 10 | | | |


# L54120 Port 212/213 Aqura Point of Use Water Meter Commodity Packet
For firmware version >= 0.6 with born on date later than Oct 13th 2022
Lora Port : 212 - Hourly , network setting ping or power up transmission
LoRa Port: 213 - Magnet triggered transmission


| Byte Index | Descriptipn | Data Type | BItmap / Notes |
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



# L54120 Port 52 Aqura Point of Use Water Meter Heath Packet

Lora Port : 52 - Once every 23 transmissions


| Byte Index | Descriptipn | Data Type | BItmap / Notes |
| --- | --- | --- | --- |
| 0 | Hardware diagnostic | 8-bit bitmap | see table 52.1 |
| 1 | Water diagnostic | 8-bit bitmap | see table 52.2 |
| 2 | Temperature fahrenheit | 8-bit unsigned int | |
| 3 | Reset code |  8-bit unsigned int  | |
| 4 | Battery voltage | 16-bit big endian unsigned int | | 
| 5 |   |   | |
| 6 | Status byte | 8-bit bitmap | see table 52.3 |
| 7 | Reset count | 16-bit big endian unsigned int  | 
| 8 | | | |
| 9 | Transmit attempt count | 16-bit big endian unsigned int | 
| 10 | | | |

## Table 52.1 : L54120 Hardware Diagnostic Byte
| Bit | Descriptipn | 
| 0 | 1 if Main Baby Board Missing, 0 if Main Baby Board is detected.|
| 1 | Undefined|
| 2 | 1 if Didn't receive NetworkKey during Join Process|
| 3 | 1 if the WaterMeter is in Aggressive Tx mode|
| 4 | 1 if Second Baby Board Missing, 0 if Second Baby Board is detected.|
| 5 | Deep Sleep Enabled (1 : Enabled via Write packet from production, 0 : disabled )|
| 6 | Undefined | 
| 7 | Undefined | 

## Table 52.2 : L54120  Water Diagnostic Byte
| Bit | Descriptipn | 
| 0 | 1 if there is no flow for 30 days, 0 when flow is detected. | 
| 1 | undefined |
| 2 | undefined |
| 3 | 1 if continuous flow for 5 hours. 0 when continuous flow is stopped |
| 4 | 1 if continuous intermittent flow for 24 hours. 0 when when cont. int. flow is stopped |
| 5 | 1 after detecting a low flow for 1 hour. 0 when low flow is stopped |
| 6 | Undefined |
| 7 | Undefined |

## Table 52.3 : L54120 Status Byte Bitmap

| Bit | Descriptipn | 
| --- | --- | 
| 7 MSB |  Magnet Flag 1 = magnet generated packet | 0 = not a magnet generated packet |
| 6,5,4 | Major firmware number |
| 3,2,1 | Minor firmware number |
| 0 |  Power up packet flag 1 = power up | 0 = not power up |


# L542xx Port 14x Series Dry Contact Pulse Meter Commodity Packet

Lora Port : 140 - Hourly , network setting ping or power up
LoRa Port: 141/145 - Magnet triggered transmission



# L542xx Port 51 Series Dry Contact Pulse Meter Heath Packet

Lora Port : 51 - Once every 23 transmissions


