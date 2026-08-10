# Here’s how to install PIA VPN!
## Official .run method (All Distros and Inits):
```
Visit and download the .run: https://www.privateinternetaccess.com/download

chmod +x ~/Downloads/[filename]
sh ~/Downloads/[filename]

(It should install and not require any services to be enabled manually)
```
## Arch AUR (Systemd only)
```
AUR Helper or Manual:
AUR helpers:
paru -S piavpn-bin
yay -S piavpn-bin
```
## Manually:
```
Dependencies: sudo pacman -S --needed base-devel git

git clone https://aur.archlinux.org/piavpn-bin.git
cd piavpn-bin
makepkg -si
```
## NOTES:
IF INSTALLED WITH EITHER AUR HELPER OR MANUALLY, ENABLE SERVICE: 
sudo systemctl enable --now piavpn.service

PIAVPN doesn’t work when you have Tailscale installed! I have not researched how to fix this, but I’m sure it isn’t that hard?
