# Overview
Common & Custom types

Legal

Mesh network fundamentals

meshtastic vs meshcore

How to setup new nodes for Meshtastic & Meshcore

Configuring Nodes

---
**What is the point?**
BIdirectional, encrypted off grid communication
Used by survivalist, hunters, ravers
Ultra low cost hardware
Monitor sensors, track objects, remote control

**What can you do with it**
Scouting,
Anti satellite warfare resilience
GPS Tracking
Encrypted disaster/emergency response
Communication between vehicles, boats & aircrt
Chat with congested cullarl service
Map and military intelligence sharing

**Defining Terms: LoRa Radio**
LoRa - The long range radio standard we use to transmit, encoding data using up and down chirps

Meshtastic - A protocol, with packets sent over LoRa, that allows for encrypoted mesh networking primarily at layer 3

**What is Meshaasitc**
Adds encyrptiom, managed floor routing, and vonevneiant apps rto Lora
* Users control nodes via bluetooth, wifi, or serial connection
* **The only thing you need to get started is a Chrome based browser**
* Managed with android

**Real World Mapping**
https://meshtastic.liamcottle.net/

Uses local MQTT collectors
* Collector nodes forward observed nodes over internet to the map via MQTT

Meshcore - ANother Layer 3 protocol introduced in 2025, designed to be more scalabale and allow for more reliable direct messaging than meshtastic.

**What is the difference**
Meshtastic is a push to telemetry sysytecm
Meshcore is a pull telemtry

Meshtastic are very noise, there's always traffic, meaning other devices can't transmit

Meshcore doesn't ahve this problem because it's quiet.

Meshtastic uses flood routing, all devices repeat traffic they hear by default
* Maxmimum of 7 hops and no defined routes means low reliablity for DMs
* Causes congestion
* Lots of unnecessary traffic in default networks

Meshcore uses static routes, floods only when needed, only repeaters repeat packets they hear.
* Manually send adverts to be discovered
* Rememebering paths prevent unnecassary flooding and scales better

*Meshcore is growing in popularity*
https://meshcore.co.uk/

**New on meshtastic for 2026**
Meshtastic is using next hop routing for DMs
Zero hop (no penalty) repeat for routers to extend range
Configure all settings via buttons

---
**Meshtastic & Meshcore ALternatives**
LoRaWAN - Uss a star topology, where end-devices (sensors) communicate directly with high power gateways. Devices only talk to the gateway

Reticulumn - A cryptography based networkign stackf ro building local and wide area networks with readily available hardware. including wifi and loRa

**Hardware Fundamentals**
LoRA Chipset - THe LoRa radio chip that controls radio transmission, such as sx35

Host Microctontroller - THe brains that run meshtastic, handle bluettoh, wifi and serial communcaitionand interface with hardwware

Breadkout Board - AN exapnsion board designed to make a bare host or radio chip more useful, breakin gout pins an dsometimes USB and power maangement

LoRa NOde - A combindation of LoRa radio and host microcontroller. TOgether, they can run Meshtastic or Meshcore

**Host + Radio = Node**

**INtrocution to LoRa**
- LoRa stands for long range, alternatice radio standard
- Radios that operate in unlicensed sub-GHz frequency bands
- SLow data rates but very long range
- Not for webcam monitoring, but ideal for telemetry, chat, control signals
*You don't need a license to use it.*

**What makes LoRa special?**
* Long range protocol uses up and down chirps to send data
* Chirp spread spectrum ,modualtion helps packets survivce noise * interference
* Successfully receive & decode packets 20 dB below the noise level
* Reci

**WHat other devices can I use**
Heltec v3, Lilygo T-Deck, Rak WIreless Wizblock,

Lilygo T-Deck, Nibble, Nugget

Heltec V3 - beginner friendly

--- 
**Regional frequencies - CHeck your radios**
North AMerica - 915 MHz (Illegal)
Theres more

**The Nibble**
Combines RP2040 or ESP32s3 host with sx1276 radio
Designed to be soldered by beginners
Select your micro: RP2040 with serial only, ......

github.com/retiallc/nibble
*Beginner friendly, souldering*

**MEs kit nibble screen connect**
Breadboard and soldering firendly kit for beginners to make thier own..

https://retia.io/blogs/news/introducing-the-nibble-zero

https://nugget.dev/ -Flash firmware for Nugget

https://client.meshtastic.org/messages/broadcast/0 - Deploys a node
* Connects to the local mesh net

---

**Device Roles**
client
client mute
* Won't repeat other peoples packets. Personal device and save battery
router
* Infrastructure 
repeater
tracker
* Good for GPS
sensor
* Good for telemtry
Tak
Client Hidden
Lost and Found
Tak Tracker

**Understand the range of Radio Profiles**
Short Range / Turbo or FAst
Medium Range
Long Range

**Adding Sensors**
IC2 Sensors supported
Look more into this, actually interesting

**Modules**
Ambient lighting
Audio
Detection Sensor
MQTT
External Notification
Paxcounter
Canned Message
Range Test
Remote Hardware
Serial Module
Store & Forward
Telemetry
Traceroute

---
# Meshcore

Download Meshcore app: https://play.google.com/store/apps/details?id=com.liamcottle.meshcore.android&hl=en_US&pli=1

For configuring meshcore device/node - https://app.meshcore.nz/

927.875 
)

**Meshcore tools**
Line of Sight

Meshcore repeater


*Consider buying a repeater*


**Local Mesh nets**
wcmesh.com
socalmesh.org
bayme.sh
centtralvalleymesh.net

---

