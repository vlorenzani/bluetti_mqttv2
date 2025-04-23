# Bluetti2MQTT-jesherman fork

This is a fork of Bluetti2MQTT which hacks together a few fixes based on prior people's own fixes so that it works as of April 2025:

- Support for encryption (thanks @nhurman!) and newer devices (e.g. AC180)
- Tweaks to fix nhurman's version of bluetti_mqtt to support the last version of asyncio_mqtt which handles filtered_messages (14.0) and adds some pip dependencies (e.g. cryptography and specific supported versions of other stuff)
- Updated python images for this addon to fix build support in GitHub
- Overall this WORKS but is very hacky! I make no warranty/guarantee but I have successfully tested it on Raspberry Pi5 running HAOS. This entire add-on probably needs a rewrite to support all the various changes that have been made to its dependencies. 


```
Add this URL to your Home Assistant Repository:

https://github.com/jesherman/bluetti2mqtt
```

Refresh the page (hard refresh may be required), scroll down to Bluetti2MQTT and install the add-on.

## Add-ons

This repository contains the following add-ons:

### [Bluetti2MQTT](./bluetti2mqtt)

![Supports aarch64 Architecture][aarch64-shield]
![Supports amd64 Architecture][amd64-shield]
![Supports armhf Architecture][armhf-shield]
![Supports armv7 Architecture][armv7-shield]
![Supports i386 Architecture][i386-shield]

[aarch64-shield]: https://img.shields.io/badge/aarch64-yes-green.svg
[amd64-shield]: https://img.shields.io/badge/amd64-yes-green.svg
[armhf-shield]: https://img.shields.io/badge/armhf-yes-green.svg
[armv7-shield]: https://img.shields.io/badge/armv7-yes-green.svg
[i386-shield]: https://img.shields.io/badge/i386-yes-green.svg

_MQTT bridge between Bluetti and Home Assistant._
