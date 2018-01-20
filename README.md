# homebridge-mqtt-sonoffrf-transmitter

Control [any RF device like this](https://www.aliexpress.com/item/EU-UK-Standard-Remote-Control-Switch-1-Gang-1-Way-RF-433Mhz-Smart-Home-Wall-Switch/32822825423.html?spm=a2g0s.9042311.0.0.j5WAco) with Homebridge using [Sonoff RF Bridge 433](https://www.itead.cc/sonoff-rf-bridge-433.html) with [TasmOTA firmware](https://github.com/arendst/Sonoff-Tasmota/wiki).

# Installation
+ Install [homebridge-mqttswitch](https://github.com/ilcato/homebridge-mqttswitch)
+ Configure the plugin in config.json with the following parameters
## config.json    
    "topics": {
      "statusGet": 	"stat/sonoff_rf/POWER",
      "statusSet": 	"cmnd/soonff_rf/RfCode"
    }
    "onValue": "#D0EC33",
    "offValue": "#D0EC44",
    
+ StatusGet will not work with one way RF device. As you can switch manually the RF device Homekit will not show the exact status of the device.
+ Insert any unique RF code for onValue and offValue 1..8388607 or hex #1..#7FFFFF
+ Start Homebridge
+ As the new switch is in Homekit do remote control pairing by turning on and off the switch in Homekit. Long press the RF device button, 2 beeps: turn Homekit switch on, 3 beeps: turn homekit swtich off.

# References
Use [homebridge-mqtt-sonoffrf-receiver](https://github.com/miskui/homebridge-mqtt-sonoffrf-receiver) to read RF sensors in Homebridge.
