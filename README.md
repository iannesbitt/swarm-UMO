# swarm-UMO
*kiosk-ready SWARM built for the University of Maine School of Earth and Climate Sciences*

Current parent SWARM version: [2.8.7](https://github.com/usgs/swarm/releases/tag/swarm-2.8.7)

# installation
*meant for Ubuntu/Kubuntu/Xubuntu but likely applicable to many UNIX OSs*

**1. Download this repository** using `git clone https://github.com/iannesbitt/swarm-UMO.git` or by using the download button on this page.

**2. Unzip** to `~/swarm-UMO`

**3. Edit your crontab** (enter `crontab -e` at a terminal window) and add the following line:
```bash
@reboot bash ~/swarm-UMO/swarm.sh "--kiosk=ORNO ew;ORNO HHZ NE 00" "--saveConfig=false" "--timeChunk=30"
```
 When you're done, press CTRL+O, Enter, and CTRL+X to save and exit the nano editor.

**4. Reboot** and ensure the kiosk begins at startup. Press the F11 key to exit or enter fullscreen kiosk mode.

### optional but recommended:

**5. Add an alias** (type `nano ~/.bash_aliases` and add the following line):
```bash
alias swarmkiosk='bash ~/swarm-UMO/swarm.sh "--kiosk=ORNO ew;ORNO HHZ NE 00" "--saveConfig=false" "--timeChunk=30" &'
```
 Again, press CTRL+O, Enter, and CTRL+X to save and exit.

**6. Type `bash` or restart your terminal window**, and now you will be able to use the alias command `swarmkiosk` to start SWARM in kiosk mode without restarting.


 about swarm
==========================

[![Build Status](https://travis-ci.org/usgs/swarm.svg?branch=master)](https://travis-ci.org/usgs/swarm)
[![Coverage Status](https://coveralls.io/repos/usgs/swarm/badge.svg?branch=master&service=github)](https://coveralls.io/github/usgs/swarm?branch=master)

Swarm is a Java application designed to display and analyze seismic waveforms in real-time. Swarm can connect to and read from a variety of different static and dynamics data sources, including Earthworm waveservers, IRIS DMCs, SEED and SAC files, and simple ASCII. Swarm has both time- and frequency-domain analysis tools, along with a simple but powerful mapping platfrom. A full-screen kiosk mode can act as a low-cost, low-maintenance replacement for paper drum recorders. Swarm was written by and for scientists and provides fine control over many different program settings and variables. The code is open source, freely available, and in the public domain.

Swarm was developed in 2004 and 2005 at the Alaska Volcano Observatory by Dan Cervelli, Peter Cervelli, Thomas Parker, and Thomas Murray. Swarm development has been in hiatus for a few years, but has recently become a priority again.
