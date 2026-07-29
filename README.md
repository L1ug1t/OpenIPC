# OpenIPC Adaptive-Link

Adaptive wireless link profile selector for OpenIPC. Adjusts only TX power on real-time signal quality from the ground station.

## Firmware

VTX Eachine sphere link imx415 update 21.07.26

ssc338q_fpv_openipc-urllc-aio-nor.tgz

VRX Eachine sphere link update 21.07.26

runcam_wifilink_sdcard.img

### Drone Installation

Copy in /etc/


## txprofile.conf

Created an ad-hoc table with MCS for each score.

## alink.conf

Changed power_level = 3

OSD level = 5

Fonts = 0.7

## wlan_adapters.yaml

Tabella mcs n. 3 con valori di power out



## Configuration

### Drone (`/etc/alink.conf`)

```ini
allow_set_power=1
use_0_to_4_txpower=1
power_level_0_to_4=0
fallback_ms=1000
osd_level=0
get_card_info_from_yaml=1
http_timeout_ms=500
```

### Ground Station (`/etc/alink_gs.conf`)

```ini
[outgoing]
udp_ip = 10.5.0.10
udp_port = 9999

[wfb-ng]
host = 127.0.0.1
port = 8103

[keyframe]
allow_idr = True
idr_max_messages = 4
idr_send_interval_ms = 20

[profile selection]
hold_fallback_mode_ms = 1000
hold_modes_down_ms = 3000
min_between_changes_ms = 200
fast_downgrade = True
upward_confidence_loops = 3

[gate]
hysteresis_up_db = 2.5
hysteresis_down_db = 1.0
snr_slope_alpha = 0.3
snr_predict_horizon_ticks = 3
emergency_loss_rate = 0.15
emergency_fec_pressure = 0.75

[dynamic]
snr_safety_margin = 3
snr_ema_alpha = 0.3
loss_margin_weight = 20
fec_margin_weight = 5
max_mcs = 5
short_gi_snr_margin = 5
utilization_factor = 0.8
max_bitrate = 24000
min_bitrate = 1000
bandwidth = 20
gop = 10

[telemetry]
log_enabled = True
log_dir = /var/log/alink
log_rotate_mb = 50
outcome_window_ticks = 10
```

## Building from Source

```bash
# Build drone daemon
make

# Run tests
make test

# Clean
make clean

# Python tests
python3 -m pytest ground-station/test/ -v
```

## Ground Station Power Settings

Set appropriate power levels for your WiFi cards (example for 8812AU):

```bash
sudo modprobe 88XXau_wfb rtw_tx_pwr_idx_override=30
```

## Documentation

- [Architecture](docs/ARCHITECTURE.md) - Technical architecture details
- [Flow](docs/FLOW.md) - Data flow documentation
- [Contributing](CONTRIBUTING.md) - Development guidelines

## License

See [LICENSE](LICENSE)