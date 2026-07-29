# OpenIPC Adaptive-Link

Adaptive wireless link profile selector for OpenIPC. Adjusts only TX power on real-time signal quality from the ground station.

## Firmware

VTX Eachine sphere link imx415 update 21.07.26

ssc338q_fpv_openipc-urllc-aio-nor.tgz

VRX Eachine sphere link update 21.07.26

runcam_wifilink_sdcard.img

## Drone Installation

Copy in /etc/


### txprofile.conf

Created an ad-hoc table with MCS for each score.

### alink.conf

Changed power_level = 3

OSD level = 5

Fonts = 0.7

### wlan_adapters.yaml

MCS Table No. 3 with power output values
