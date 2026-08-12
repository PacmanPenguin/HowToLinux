# DNS Caching with NetworkManager (Any Init):
**Install dnsmasq:**
```
Arch: sudo pacman -S dnsmasq
Debian: sudo apt install dnsmasq
Fedora: sudo dnf install dnsmasq
openSUSE: sudo zypper install dnsmasq
```
**Configure NetworkManager:**
```
sudo nano /etc/NetworkManager/NetworkManager.conf

Paste in:
[main]
dns=dnsmasq

Make the Directory:
sudo mkdir -p /etc/NetworkManager/dnsmasq.d

Make the cache larger:
echo "cache-size=1000" | sudo tee /etc/NetworkManager/dnsmasq.d/cache.conf
```
**Restart NetworkManager:**
```
OpenRC: sudo rc-service NetworkManager restart
Systemd: sudo systemctl restart NetworkManager
SysVinit: sudo service NetworkManager restart
```
**Verify it worked:**
```
time getent hosts artixlinux.org && time getent hosts artixlinux.org
```
(second output should be faster than the first)

# DNS Caching with ConnMan (Any Init)
```
sudo ln -sf /run/connman/resolv.conf /etc/resolv.conf
```
**Verify it worked:**
```
time getent hosts artixlinux.org && time getent hosts artixlinux.org
```
