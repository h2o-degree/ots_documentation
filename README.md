

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
| 4 | Battery voltage | 16-bit big endian unsigned int | value / 256 | 
| 5 |   |   | |
| 6 | Status byte | 8-bit bitmap | see table 52.3 |
| 7 | Reset count | 16-bit big endian unsigned int  | 
| 8 | | | |
| 9 | Transmit attempt count | 16-bit big endian unsigned int | 
| 10 | | | |


# L542xx Port 14x Series Dry Contact Pulse Meter Commodity Packet

Lora Port : 140 - Hourly , network setting ping or power up
LoRa Port: 141/145 - Magnet triggered transmission



# L542xx Port 51 Series Dry Contact Pulse Meter Heath Packet

Lora Port : 51 - Once every 23 transmissions


