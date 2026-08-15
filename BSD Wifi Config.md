I know this is BSD not Linux but I need to write this down
# Configuring WiFi with WPA Supplicant on FreeBSD
Get your device name:
```
sysctl net.wlan.devices
```
Create the interface (likely already exists but still):
```
ifconfig wlan0 create wlandev [device name]
```
Configre WiFi info:
```
wpa_passphrase "YourSSID" "YourPassword" > /etc/wpa_supplicant.conf
```
Paste this into /etc/rc.conf:
```
devmatch_blocklist="if_iwm"
wlans_iwn0="wlan0"
ifconfig_wlan0="WPA SYNCDHCP up"
```
Now reboot! 
