# Sonoff

Control ITEAD Sonoff WiFi devices using Homey.

### Introduction

This driver works with unmodified Sonoff WiFi devices, using the original firmware (however, see below).

However, it does require an initial device setup. The procedure for this is documented in [`README.md`](https://github.com/robertklep/name.klep.sonoff#readme), and you can also read it during the device pairing phase on Homey.

It does not require the Sonoff/eWeLink app on your mobile. Once the device has been set up, it will also not use the Sonoff/eWeLink Chinese cloud (instead, it will use Homey as its cloud server).

Be aware that as long as the device is associated with Homey, you can't use it with the eWeLink app anymore. To revert back to using the eWeLink app, re-pair the device with the app.

### New Sonoff Firmware may break this app's functionality!

Recently, new Sonoff firmware updates have been released that prevent this app from working. This means two things:

* Newer, or recently purchased, devices may not work with this app at all.
* If you have an older device, but update its firmware through the eWeLink app, it may not be possible to get the device working with Homey anymore.

As of yet, there is no solution to this problem. Other projects that work in a similar way, like [SonOTA](https://github.com/mirko/SonOTA/issues/87), are also faced with this problem.

As an alternative, this app supports Sonoff devices running the (unofficial) [Sonoff-Tasmota](https://github.com/arendst/Sonoff-Tasmota/) firmware. However, installing an alternative firmware requires you to open up the device (voiding its warranty), soldering connectors to it, and flashing the firmware using a USB-to-serial dongle. It also requires an MQTT broker to be running; you can use the Homey [MQTT Broker](https://apps.athom.com/app/nl.scanno.mqttbroker) app for this.

### Tested devices

This driver has been tested with the following devices:

* Sonoff Basic WiFi Wireless Switch (original firmware)
* Sonoff S20 Smart Socket (original firmware and Sonoff-Tasmota)
* Sonoff RF WiFi Wireless Smart Switch With RF Receiver (original firmware)
* Sonoff Slampher (original firmware)
* Sonoff RF Bridge (Sonoff-Tasmota)

Support for features besides switching the device on/off (i.e. timers, temperature/humidity/power sensors) is limited.

For the Sonoff RF Bridge running the Sonoff-Tasmota firmware, sending and receiving 433Mhz codes is supported.

### Issues

Please report issues here: https://github.com/robertklep/name.klep.sonoff/issues

### Changelog

3.0.0 (2018-03-05):
- Rewritten Tasmota MQTT client
- Try to automatically identify newly paired device (to provide correct icon)

2.1.0 (2018-02-19):
- Support for receiving/transmitting RF codes (with the Sonoff RF Bridge running the Tasmota firmware)

2.0.1 (2018-02-09):
- Better MQTT broker offline handling

2.0.0 (2018-02-05):
- Support for Sonoff-Tasmota firmware

1.3.0 (2018-01-23):
- Ability to set up a fresh Sonoff device through the Homey desktop app, instead of having to use `curl`

1.2.0 (2017-12-16):
- Improved pairing
- Using icon set kindly provided by Ivo Derksen

1.1.0 (2017-12-09):
- Rewritten device manager
- Added device watchdog to faster catch devices that went offline
- Added syslog support as development aid
- Faster pairing in certain situations

1.0.0 (2017-12-01):
- Initial beta release
