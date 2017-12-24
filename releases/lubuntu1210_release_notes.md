# lubuntu 12.10 Release Notes

## New Features in Lubuntu 12.04

This release of Lubuntu contains:

- Update of the visual identity of Lubuntu, including :
  - A completely new icon theme.
  - A new wallpaper and improvements to the current theme.
  - A selection of community wallpapers.
  - Improving integration of many applications with the new artwork.
- A new version of the session manager is available, including more customizations and integration options (not enable by default, but available for testing).
- A new version of pcmanfm (file manager), including at lot of bug fixes, external thumbnailer support, multiple screen support.
- Notification-daemon have been replaced for xfce4-notifyd on the default installation, to display notifications.
- Catfish, a searching utility, have been added to the default installation.

## Lubuntu Applications
- Based on the lightweight LXDE desktop environment.
- Pcmanfm, a fast and lightweight files manager using gio/gvfs.
- [Openbox](http://openbox.org/), the fast and extensible, default windows-manager of LXDE.
- Lightdm, using the simple GTK greeter
- Chromium, the open-source version of Google Chrome.
- For more detail, please see the [full list of applications](https://wiki.ubuntu.com/Lubuntu/Applications)
<hr>

## System Requirements
A Pentium II or Celeron system with 128 MB of RAM is probably a bottom-line configuration that may yield slow yet usable system with a standard lubuntu desktop.

12.10 32 bit ISO require your CPU to have Physical Address Extensions, or PAE. "PAE is provided by Intel Pentium Pro and above CPUs, including all later Pentium-series processors (except most 400 MHz-bus versions of the Pentium M)." - If you have a NON-PAE CPU and would like to install Lubuntu 12.10, please see [this link](http://www.webupd8.org/2012/11/how-to-install-ubuntu-1210-on-non-pae.html) or you can use Lubuntu 12.04 instead.

For PowerPC, it is known to run on a G4 running at 867MHz with 640MB RAM.

For Intel based Macs, lubuntu should run on all models.

## Download
To download Lubuntu and see the various options available head over to [Get Lubuntu](lubuntu1204_downloads.md). This section also discusses both the standard installs and those required for computers with low memory (RAM), old chipsets (i586), PowerPC, Mac and low disk-space (netbooks).

<hr>

## Known Issues

### Installation

PPC has several issues and workarounds, please refer to the [documentation on the wiki](https://help.ubuntu.com/community/Lubuntu/Documentation/FAQ/PPC)

### Graphics and Display

On some GTK3 applications, some tooltips have a black background and a black font. ([1065941](https://bugs.launchpad.net/bugs/1065941))

### Applications

- Execute in terminal is not working in pcmanfm ([975152](https://bugs.launchpad.net/bugs/975152))

- Blank boxes appear when hardinfo is started, and needed to be closed before accessing to the application ([1029212](https://bugs.launchpad.net/bugs/1029212))

- Different spacing for the icons on the right corner of lxpanel ([1056547](https://bugs.launchpad.net/bugs/1056547))

- Software sources takes 30 seconds to load ([1051723](https://bugs.launchpad.net/bugs/1051723))

- Clicking on Ibus icon start the deamon, but doesn't display an icon ([1041933](https://bugs.launchpad.net/bugs/1041933))

- gnome-mplayer with mplayer2 is not working on some hardware. Installing mplayer package workaround the problem ([858226](https://bugs.launchpad.net/bugs/858226), [974125](https://bugs.launchpad.net/bugs/974125), [987734](https://bugs.launchpad.net/bugs/987734))

- Calling file-roller inside pcmanfm doesn't work ([978789](https://bugs.launchpad.net/bugs/978789))
<hr>

## Support
18 Months
<br>
