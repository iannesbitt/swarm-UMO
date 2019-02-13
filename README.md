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


# troubleshooting
Use the `tree` command to examine the directory structure. `tree` should be pretty common on unix machines, but if you don't have it it's likely easy to get with `sudo apt-get install tree`, `sudo pacman -S tree`, or `brew install tree` depending on your OS.

The point of `tree` is to figure out whether your unzip worked correctly. The meat of SWARM should reside in `~/swarm-UMO` for things to work properly. If instead things unzip to `~/swarm-UMO/swarm-UMO`, or for whatever reason things get moved around, the commands described above won't be able to find their targets.

Your output should look like the following:
```
$ tree ~/swarm-UMO
.
├── CHANGES.md
├── clip.wav
├── DefaultVelocityModel.txt
├── ding.wav
├── docs
│   ├── hypo71manual.pdf
│   └── swarm_v2.pdf
├── EventClassifications.config
├── Hypo71.config
├── layouts
│   └── ORNO.config
├── lib
│   └── swarm.jar
├── LICENSE.md
├── mapdata
│   ├── augustine
│   │   ├── augustine_10m.png
│   │   └── MapPack.txt
│   ├── nasa_240m_A1
│   │   ├── MapPack.txt
│   │   └── nasa_240m_A1_F_07.jpg
│   ├── nasa_240m_D2
│   │   ├── MapPack.txt
│   │   ├── nasa_240m_D2_D_10.jpg
│   │   ├── nasa_240m_D2_E_09.jpg
│   │   ├── nasa_240m_D2_E_10.jpg
│   │   └── nasa_240m_D2_F_09.jpg
│   ├── nasa_2k
│   │   ├── MapPack.txt
│   │   ├── nasa_2k_B_01.jpg
│   │   ├── nasa_2k_B_02.jpg
│   │   ├── nasa_2k_B_10.jpg
│   │   ├── nasa_2k_C_01.jpg
│   │   ├── nasa_2k_C_02.jpg
│   │   ├── nasa_2k_C_10.jpg
│   │   ├── nasa_2k_G_10.jpg
│   │   └── nasa_2k_H_10.jpg
│   └── world
│       ├── Labels.txt
│       ├── MapPack.txt
│       ├── world_A1.jpg
│       ├── world_A2.jpg
│       ├── world_A3.jpg
│       ├── world_A4.jpg
│       ├── world_B1.jpg
│       ├── world_B2.jpg
│       ├── world_B3.jpg
│       ├── world_B4.jpg
│       └── world.jpg
├── NTP.config
├── README.md
├── Swarm.config
├── Swarm.config.bak
├── swarm_console.bat
├── swarm.sh
└── WaveDefaults.config

9 directories, 47 files
```

## java

You shouldn't have problems with errors in Java itself, but it does need to be installed if it's not already. It's likely already installed on many OS environments (you can check by trying `java -version` at a command prompt). If it's not, follow instructions for your OS to install it (graphical installer for Mac, `sudo apt install default-jdk` for Ubuntu, `pacman -S jre-openjdk` for Arch.

## other issues?

Please [open a new github issue](https://github.com/iannesbitt/swarm-UMO/issues/new) describing the problem, the OS, and the output of the following commands:

```bash
tree ~/swarm-UMO
bash ~/swarm-UMO/swarm.sh
```


 about swarm
==========================

[![Build Status](https://travis-ci.org/usgs/swarm.svg?branch=master)](https://travis-ci.org/usgs/swarm)
[![Coverage Status](https://coveralls.io/repos/usgs/swarm/badge.svg?branch=master&service=github)](https://coveralls.io/github/usgs/swarm?branch=master)

Swarm is a Java application designed to display and analyze seismic waveforms in real-time. Swarm can connect to and read from a variety of different static and dynamics data sources, including Earthworm waveservers, IRIS DMCs, SEED and SAC files, and simple ASCII. Swarm has both time- and frequency-domain analysis tools, along with a simple but powerful mapping platfrom. A full-screen kiosk mode can act as a low-cost, low-maintenance replacement for paper drum recorders. Swarm was written by and for scientists and provides fine control over many different program settings and variables. The code is open source, freely available, and in the public domain.

Swarm was developed in 2004 and 2005 at the Alaska Volcano Observatory by Dan Cervelli, Peter Cervelli, Thomas Parker, and Thomas Murray. Swarm development has been in hiatus for a few years, but has recently become a priority again.
