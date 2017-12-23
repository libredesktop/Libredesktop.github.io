# lubuntu 12.04 Release Notes

## New Features in Lubuntu 12.04

This release of Lubuntu contains:

- A new software-center, optimized to be lightweight, for easy installation and removal of applications from your system.

## Lubuntu Applications
* [LXDE](http://lxde.org), the lightweight desktop environnement, including applications such as Pcmanfm and LXAppearance.
* [Openbox](http://openbox.org), the fast and extensible, default windows-manager of LXDE.
* Chromium, the open source version of the Google browser Chrome.
* For more detail, please see the [full list of applications](https://wiki.ubuntu.com/Lubuntu/Applications)
<hr>

## System Requirements
A Pentium II or Celeron system with 128 MB of RAM is probably a bottom-line configuration that may yield slow yet usable system with a standard lubuntu desktop.

Default i686 (32 bit) images support more hardware than the equivalent Ubuntu image, as it uses a non-PAE kernel, but is limited to 4 GB of memory. If you have more than 4 GB of memory on a 32 bit system, head over to Get Lubuntu for a fuller discussion.

For PowerPC, it is known to run on a G4 running at 867MHz with 640MB RAM.

For Intel based Macs, lubuntu should run on all models.

## Download
To download Lubuntu and see the various options available head over to [Get Lubuntu](lubuntu1204_downloads.md). This section also discusses both the standard installs and those required for computers with low memory (RAM), old chipsets (i586), PowerPC, Mac and low disk-space (netbooks).

<hr>

## Known Issues

### Installation

Broken icon falsely indicates reducing the size of a partition is not possible. ([986607](https://bugs.launchpad.net/bugs/986607))

### Graphics and Display

None

### Applications

- gnome-mplayer may crash on some specific hardware (Pentium 3 or Pentium 4). Installing the package mplayer should work-around the problem. ([974125](https://bugs.launchpad.net/bugs/974125))

- lxkeymap may crash on certain keyboard configuration. ([945603](https://bugs.launchpad.net/bugs/945603))
<hr>

## Changes since 11.10

- New [artwork](http://packages.ubuntu.com/precise/lubuntu-artwork) is used.

- Lubuntu 12.04 now uses Lightdm as the display manager with the [lightdm-gtk-greeter](http://packages.ubuntu.com/precise/lightdm-gtk-greeter).

- [Blueman](http://packages.ubuntu.com/precise/blueman) is now used instead of gnome-bluetooth for managing bluetooth devices.

## Support
This release is supported for 18 months (12.04 Lubuntu is not an LTS).
<br>
