# lubuntu 15.04 Release Notes

## New Features in Lubuntu 15.04

* General bug fix release as we prepare for LXQt.
* Many LXDE components have been updated with bug fix releases.
* An update of the artwork (more icons, theme update, more compatibilities …).


---

## Lubuntu Applications

* Based on the lightweight [LXDE desktop environment](https://lxde.org/).
* [Pcmanfm](https://wiki.lxde.org/en/PCManFM), a fast and lightweight files manager using gio/gvfs.
* [Openbox](https://openbox.org), the fast and extensible, default windows-manager of LXDE.
* [Lightdm](https://launchpad.net/lightdm), using the simple GTK greeter
* Firefox, the famous web browser.
* For more detail, please see the [full list of applications](https://help.ubuntu.com/community/Lubuntu/Setup#Applications).

---

## System Requirements

Lubuntu is a good operating system for many old computers, but not for all of them. Some computers have too little horsepower or memory. A rule of thumb is that the computer should not be more than 10 years old.

### **Memory (RAM)**

For advanced internet services like Google+, Youtube, Google Docs and Facebook, your computer needs about 1 GB RAM.

For local programs like Libre Office and simple browsing habits, your computer needs about 512 MB RAM. See [minimal](https://help.ubuntu.com/community/Lubuntu/Documentation/MinimalInstall) for systems below that RAM.

### **Processor (CPU)**

The minimum specification for CPU is Pentium 4 or Pentium M or AMD K8.

Older processors are too slow and AMD K7 has problems with flash video.

### **Graphics chip / card**

Nvidia, AMD/ATI/Radeon and Intel work out of the box, or the system can be tweaked to work fairly easily. You can get help at the [Ubuntu Forums](https://ubuntuforums.org/). With such graphics, or if you don’t know, try the current Lubuntu version.

---

## Known Issues

### **Installation**

* Desktop installer does not reboot or shutdown when prompted at the end of the install in [VirtualBox](https://wiki.ubuntu.com/VirtualBox) or VMWare, so a hard shutdown will be required ([1447038](https://bugs.launchpad.net/ubuntu-mate/+bug/1447038)).
* Desktop installer fails to load desktop window decorations on Haswell Intel desktop with HD 4600 graphics ([1445814](https://bugs.launchpad.net/ubuntu/+source/lxsession/+bug/1445814)).


### **Desktop**

* run dialog opens on desktop with lxpanel config not current desktop ([1445818](https://bugs.launchpad.net/ubuntu/+source/lxpanel/+bug/1445818)).
* notification dialog has horizonal bars; workaround exists ([1362555](https://bugs.launchpad.net/ubuntu/+source/lubuntu-artwork/+bug/1362555)).
* lxpanel volume applet settings opens empty terminal window; workaround exists ([1434774](https://bugs.launchpad.net/ubuntu/+source/lxsession/+bug/1445814)).

### **Applications**

* lubuntu-software-center: can’t find uninstalled packages on a system installed with the alternate image; workaround exists ([1446830](https://bugs.launchpad.net/ubuntu/+source/lubuntu-software-center/+bug/1446830)).
* file-roller: “Add files” greyed out, can’t add anything ([1383902](https://bugs.launchpad.net/ubuntu/+source/file-roller/+bug/1383902)).
* file-roller when launched from context menu of pcmanfm has password filed grayed out when creating a compressed archive ([1432777](https://bugs.launchpad.net/ubuntu/+source/file-roller/+bug/1432777)).
* gnome-mplayer shows 2 notifications for opening multiple files when window is not focused ([1434347](https://bugs.launchpad.net/ubuntu/+source/gnome-mplayer/+bug/1434347)).

### **PPC**

* Lubuntu PPC is now [LTS](https://wiki.ubuntu.com/LTS) only.

---

## Ubuntu Release notes

* For a full list of issues and features common to Ubuntu, please refer to the [Ubuntu release notes](https://wiki.ubuntu.com/WilyWerewolf/ReleaseNotes).

---

### **Support**

* 9 months support
