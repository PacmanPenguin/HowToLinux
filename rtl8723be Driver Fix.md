(My tests have been done on the HP Stream 13, but this should work on every device with the Realtek Wi-Fi card that uses the rtl8723be driver.)
# Getting WiFi working on rtl8723be (HP Stream 13)!
### Driver Fix:
```
echo "options rtl8723be ant_sel=1 fwlps=0 ips=0 swenc=1" | sudo tee /etc/modprobe.d/rtl8723be.conf
```
### Apply Immediately:
Option 1:
```
sudo rmmod rtl8723be && sudo modprobe rtl8723be
```
Option 2:
```
sudo reboot
```
