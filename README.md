# Dynamic BED_MESH_CALIBRATE for RatOS
Klipper mesh on print area only (RatOS adaptation)

## Credit
Complete credit goes to ChipCE (https://gist.github.com/ChipCE/95fdbd3c2f3a064397f9610f915f7d02) for the idea and sample code.\
Idea to make it as repository goes to Turge08 (https://github.com/Turge08).

I only remixed it (well, and slightly modified it. It is mostly syntactic sugar anyway).

## Setup
### 1. Download and install the macro
SSH into the RPi and run the following commands:
```
cd ~
git clone https://github.com/kmarty/Dynamic_BED_MESH_CALIBRATE.git
```
### 2. Include macro in your printer.cfg
After lines:
```
### USER OVERRIDES
# Place all your overrides here
```
add the following:
```
[include /home/pi/Dynamic_BED_MESH_CALIBRATE/BED_MESH_CALIBRATE.cfg]
```
### 3. Update Moonraker for easy updating
From Fluidd/Mainsail, edit moonraker.conf (in the same folder as your printer.cfg file) and add:
```
[update_manager Dynamic_BED_MESH_CALIBRATE]
type: git_repo
path: ~/Dynamic_BED_MESH_CALIBRATE
origin: https://github.com/kmarty/Dynamic_BED_MESH_CALIBRATE.git
is_system_service: False
```
NOTE: You must perform step #1 at least once or Moonraker will generate an error.

TODO
