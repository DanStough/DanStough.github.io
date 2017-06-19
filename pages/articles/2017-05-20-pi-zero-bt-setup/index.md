---
title: Setting up a Bluetooth PAN on the rPi Zero W
date: "2017-05-20T221:43:00.000Z"
layout: post
path: "/articles/2015-05-28-hi-folks/"
category: "Hardware"
description: "TBD."
---

Things to try:
Hooking up on Windows 
Build newest version of Bluez

### Intro



### General Setup

This process is the same regardless of the chosen operating system.

1. Boot with NOOBS, select Raspian
1. Connect to internet access
1. sudo apt-get update
1. sudo apt-get upgrade
1. sudo apt-get install rpi-update
1. sudo rpi-update
1. restart
1. sudo systemctl start ssh
1. sudo systemctl enable ssh
1. (Connect via Bluetooth gives you errors): Troubleshooting either: sudo systemctl status bluetooth OR grep bluetooth /var/log/systemd
    1. SAP Plugin failed
    1. Audio sink disabled
1. Setup Audio (https://github.com/ev3dev/ev3dev/issues/198)
    1. Make sure to enable service so it begins on startup
    1. Optional fix SAP Plugin
1. Connect (Steps Below)
1. Start NAP
    1. (https://www.raspberrypi.org/forums/viewtopic.php?f=28&t=160672&p=1041564)
        1. install test scripts
        1. sudo apt-get python-pip
        1. pip install dbus


Bluetoothctl Setup Steps
1. bluetoothctl
    1. power on
    1. agent on
    1. default-agent (negotiate pairring code)
    1. discoverable on

### Setup using Raspian (Pixel)

Make sure your wireless connection is still accessible from startup.

### Setup using Raspian Lite


### Additional Notes

* ```bluez-test-scripts```, when installed, can be accessible at /usr/share/doc/bluez-test-scripts/.
    * The[ test-network script](https://www.raspberrypi.org/forums/viewtopic.php?f=28&t=160672&p=1041564) can be used to create a PAN connection similar to the bt-pan script.
* [Setup from start to finish](https://www.raspberrypi.org/forums/viewtopic.php?f=28&t=138145&start=25)
* [Install python dbus script dependency](http://stackoverflow.com/questions/37521162/how-solve-importerror-no-module-named-dbus)
* [Test Network instrucions](https://www.raspberrypi.org/forums/viewtopic.php?f=28&t=160672&p=1041564)
* [The bt-pan script for connecting once paired; can be replaced by bluez-tools bt-network?](https://github.com/mk-fg/fgtk/blob/master/bt-pan)


### Resources

* [ArchLinux Description of Bluetooth Linux tools (aka Bluez)](https://wiki.archlinux.org/index.php/Bluetooth#Bluetoothctl)
* [Youtube Video of Raspian Group Network Setup](https://www.youtube.com/watch?v=4Ac0wc-f9HI)
* [This is the most current PAN tutorial I have found, albeit a little obtuse.](http://blog.fraggod.net/2015/03/28/bluetooth-pan-network-setup-with-bluez-5x.html)
* [Additional commentary on the aforemention link](https://blind.guru/tag/bluetooth-pan.html)
* [Out of the box issues with Audio profile connects and resolution through Pulseaudio](https://raspberrypi.stackexchange.com/questions/44497/having-an-issue-with-bluetooth-manager-pairing-on-the-pi)
* [Adafruit's concise description of building Bluez from source](https://learn.adafruit.com/install-bluez-on-the-raspberry-pi/installation)
* [Permission issues associated with the 'bluetooth' group on the full Raspian Bluetooth manager + rpi setup](https://www.pi-supply.com/make/fix-raspberry-pi-3-bluetooth-issues/)
* [Bluetooth PAN between IPhone and MacOS](https://www.atpeaz.com/fixing-the-iphone-bluetooth-internet-tethering-with-os-x/)
* [Removing Bluez SAP Plugin error by disabling the service plugin](https://raspberrypi.stackexchange.com/questions/40839/sap-error-on-bluetooth-service-status)
* [More Audio Profile issues](https://askubuntu.com/questions/440386/bluetoothd-bluez-5-wont-connect-with-any-devices)
* [Pulse audio complete setup](https://github.com/ev3dev/ev3dev/issues/198)
* [Troubleshooting Logs](https://www.raspberrypi.org/forums/viewtopic.php?f=29&t=123744&p=831380&hilit=bluez+5.23#p831380)

sudo apt-get update
sudo apt-get install -y libusb-dev libdbus-1-dev libglib2.0-dev libudev-dev libical-dev libreadline-dev