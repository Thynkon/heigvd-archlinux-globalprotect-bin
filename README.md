# GlobalProtect VPN Client Installer for ArchLinux

This repo contains `PKGBUILD` for Arch Linux for installing Palo Alto Network's 
GlobalProtect VPN Client app, in order to connect to 
[HEIG-VD](https://heig-vd.ch) VPN.


This `PKGBUILD` requires the source Ubuntu installer package (`.deb`), which can 
be downloaded from [HEIG-VD VPN](https://vpn.heig-vd.ch).

Download the Linux version and extract its content. Then, copy the `GlobalProtect_UI_focal_deb_<VERSION>.deb` file to the same directory as the `PKGBUILD` file.

Then, run the following command to build and install the package:

```bash
$ makepkg -si
```

Update the `sha256sums` appropriately.
It is also assumed that you are [building in a clean chroot](https://wiki.archlinux.org/title/DeveloperWiki:Building_in_a_clean_chroot) 
and have the [pre-requisites installed](https://wiki.archlinux.org/title/Creating_packages#Prerequisite_software).

One of the required dependencies is [qt5-webkit](https://aur.archlinux.org/packages/qt5-webkit)<sup>AUR</sup>, 
however, it takes very long to build that package. 
You may choose to install the [pre-built binary](https://aur.archlinux.org/packages/qt5-webkit#comment-896552) released 
by the current maintainer of that AUR package (FabioLolix as of 2023/09/20).
