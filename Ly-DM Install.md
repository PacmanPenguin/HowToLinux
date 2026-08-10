# How to install Ly-DM?
## Official Repos (Likely Systemd Only):
```
Using your distro’s package manager, attempt to install the package “ly”, if it is found, install it and then enable it:
sudo systemctl enable ly@tty2.service
sudo systemctl disable getty@tty2.service
```
## Systemd (Any Distro):
```
(Zig may not be in your repos, if it isn’t you’re on your own to install zig manually sorry)
Install required packages:
sudo pacman -S git zig
sudo apt install git zig
sudo dnf install git zig
sudo zypper install git zig
```
Install Ly:
```
git clone https://codeberg.org/fairyglade/ly.git
cd ly
zig build
sudo zig build installsystemd
sudo systemctl enable ly@tty2.service
sudo systemctl disable getty@tty2.service
```
## OpenRC (Any Distro):
```
(Zig may not be in your repos, if it isn’t you’re on your own to install zig manually sorry)
Install required packages:
sudo pacman -S git zig
sudo apt install git zig
```
Install Ly:
```
git clone https://codeberg.org/fairyglade/ly.git
cd ly
zig build
sudo zig build installexe -Dinit_system=openrc
sudo rc-update add ly default
sudo rc-update del agetty.tty2

(If you use LightDM before):
sudo rc-update del lightdm 2>/dev/null || true
```
