kilnController
Turns a Raspberry Pi 4 into a Beast, it's universal & is a web-enabled kiln Controller. Forked from the reflow oven project: picoReflow i found first through Chrono and kilncontroller which I found through botheredbybees/kilnController https://github.com/botheredbybees/kilnController

I Tried and Tested this Awesome software on many kilns it has manual tuning at the moment which is not that difficult and gets a better result in the end fine tuning anyhow , you can control and check progress on my mobile phone or PC. If you already know your kilns PID setting it makes it easy or you can use/borrow a cheap PID set point controller with Auto tune to get settings it works :)

Kiln Control Software has Almost unlimited Ramps/Stages and Temperature Range Depending on sensor Type Has Thermocouple Short to ground and no connection protection(so firing will stop if errors are encounted) Control from anywhere in the world over multiple devices Data Log by screen shoting the graph Over time you can use this data to see how much you elements are wearing at the top end this applies mostly to stoneware firings

So Far Tested on HPF4 Ward Kiln ,Paragon TNF82 , AFC 10CFT Rebnick 18" kiln and many more , works best with thermocouple close to elements and no ceramic sheath/well easier to tune.

It can not only heat stuff it can chill as well!! use long cycle times on cooling mode so to not damage fridge or freezer motors

Updating Software I will Try to add Auto tuning in the future! but please don't hesitate to help

External dependencies have been kept to a minimum to make it easily deployable on any flavor of open-source operating system.

Currently tested versions
greenlet-0.4.2
bottle-0.12.4
gevent-1.0
gevent-websocket-0.9.3
Ubuntu/Raspbian
$ sudo apt-get install python-pip python-dev libevent-dev
$ sudo pip install ez-setup
$ sudo pip install greenlet bottle gevent gevent-websocket
Gentoo
$ emerge -av dev-libs/libevent dev-python/pip
$ pip install ez-setup
$ pip install greenlet bottle gevent gevent-websocket
Raspberry PI deployment
If you want to deploy the code on a PI for production:

$ pip install RPi.GPIO
This only applies to non-Raspbian installations, since Raspbian ships RPi.GPIO with the default installation.

If you also want to use the in-kernel SPI drivers with a MAX31855 sensor:

$ sudo pip install Adafruit-MAX31855
Clone repo
$ git clone https://github.com/Brett309/kilnController.git
$ cd kilnController
Configuration
All parameters are defined in config.py. There's a copy in config.py.EXAMPLE so you can review and change things to your heart's content.

Usage
Server Startup
$ cd kilnController
$ python kilncontrollerd.py
Autostart Server onBoot
If you want the server to autostart on boot, run:

sudo nano /etc/rc.local
add the line:

`sudo python /home/pi/kilnController/kilncontrollerd.py &`
Client Access
Open Browser and goto http://127.0.0.1:8081 (for local development) or the IP of your PI and the port defined in config.py (default 8080).

License
This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see http://www.gnu.org/licenses/.

picoReflow
For more info on the parent project, see picoReflow: https://apollo.open-resource.org/mission:resources:picoreflow
