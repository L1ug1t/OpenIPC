# OpenIPC Adaptive-Link

Adaptive wireless link profile selector for OpenIPC. Adjusts only TX power on real-time signal quality from the ground station.

## Firmware

VTX Eachine sphere link imx415 update 21.07.26

ssc338q_fpv_openipc-urllc-aio-nor.tgz

VRX Eachine sphere link update 21.07.26

runcam_wifilink_sdcard.img

## Drone Installation

Install WinSCP, Connect the VTX to the router using the LAN cable, and look up your IP address in the router settings.

WinSCP -> Tabs -> New Tab -> File Protocol = scp - Host Name = your IP - User Name = root - Password = 12345 

Copy files in /etc/


### txprofile.conf

Created an ad-hoc table with MCS for each score.

MCS = 0 - 3

fec = 8 - 12

bitrate = 8000 to 4000

gop = 10

Pwr = don't work

roiQp = 0,0,0,0

bandwidth = 20

qpDelta = -12


These values ​​are for long-range use, aiming for a decent video feed with a minimum bitrate. 
It can also work for Acro mode.


### alink.conf

Changed power_level = 3

OSD level = 5

Fonts = 0.7

### wlan_adapters.yaml

MCS Table No. 3 with power output values

### Set 60 fps in OpenIPC VRX menu'

I am using these files and managing to reach 5 km without glitches or video interruptions caused by the firmware; any reception issues would simply be due to the antennas used and their alignment.
I use the stock antennas on the VTX and two DIY 16 element Yagi antennas (for 5.8 GHz) on the VRX. With two patch antennas I think a range of 3–4 km is achievable.
I’ve only been testing for two days and don’t have the batteries to go any further; I’m getting a 5 km range (each way) with my 200g quad, 1104 motors, HQ 3.5x2.2 props, and dual 3000mAh 18650 Li-ion batteries.