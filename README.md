# OpenIPC
Long Range

Il mio setup per adaptive link con potenza di uscita per VTX variabile

Bitrate: 8 - 4 Mbps

Channel Width: 20 MHz

MCS: 0 - 3

FEC: 8/12

Guard Interval: long 



Modifiche su:

/etc/txprofiles.conf

/etc/alink.conf

/etc/wlan_adapters.yaml


Txprofile.conf

Creato tabella ad hoc con mcs per ogni score

Alink.conf

Modificato power_level = 3

Osd level = 5

Font = 0.7


Copiare i file sulla VTX in /etc/



wlan_adapters.yaml

Tabella mcs n. 3 con valori di power out

