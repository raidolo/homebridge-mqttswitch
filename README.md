# homebridge-mqttswitchplus
An homebridge plugin that create an HomeKit Switch accessory mapped on MQTT topics

# Installation
Follow the instruction in [homebridge](https://www.npmjs.com/package/homebridge) for the homebridge server installation.
The plugin is published through [NPM](https://www.npmjs.com/package/homebridge-mqttswitchplus) and should be installed "globally" by typing:

    npm install -g homebridge-mqttswitchplus

# Instructions
This plugin uses a status command, sent via the "set" Topic, to dinamically retrieve the status of the switch from the device. 
The status should be sent by the device on the "get" topic, as usual. 
You should develop the device code to accept the status command on the "set" topic and answer publishing the actual status using the "get" topic. 

# Release Notes
Version 0.0.1
+ Introduced the status command to dynamically read the status of the switch

# Forked by ilcato/homebridge-mqttswitch - Previous Release notes
Version 0.0.3
+ Added onValue, offValue and integerValue params

Version 0.0.2
+ Initial public draft

# Configuration
Remember to configure the plugin in config.json in your home directory inside the .homebridge directory. Configuration parameters:
+ "accessory": "mqttswitch",
+ "name": "PUT THE NAME OF YOUR SWITCH HERE",
+ "url": "PUT URL OF THE BROKER HERE",
+ "username": "PUT USERNAME OF THE BROKER HERE",
+ "password": "PUT PASSWORD OF THE BROKER HERE",
+ "caption": "PUT THE LABEL OF YOUR SWITCH HERE",
+ "topics": {
 	"statusGet": 	"PUT THE MQTT TOPIC FOR THE GETTING THE STATUS OF YOUR SWITCH HERE",
 	"statusSet": 	"PUT THE MQTT TOPIC FOR THE SETTING THE STATUS OF YOUR SWITCH HERE"
	}
+ "onValue": "OPTIONALLY PUT THE VALUE THAT MEANS ON HERE (DEFAULT true)",
+ "offValue": "OPTIONALLY PUT THE VALUE THAT MEANS OFF HERE (DEFAULT false)",
+ "statusCmd": "OPTIONALLY PUT THE STATUS COMMAND HERE",
+ "integerValue": "OPTIONALLY SET THIS TRUE TO USE 1/0 AS VALUES"

Look for a sample config in [config.json example](https://github.com/raidolo/homebridge-mqttswitchplus/blob/master/config.json)
