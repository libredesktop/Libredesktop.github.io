# lubuntu 15.10 Release Notes

## New Features in Lubuntu 15.10

* General bug fix release as we prepare for LXQt.
* Many LXDE components have been updated with bug fix releases.
* An update of the artwork (more icons, theme update, more compatibilities).
* The problematical iBus has now been replaced with Fcitx. With that change the fonts for Chinese, Japanese and Korean have been added back into the build.
* lubuntu-extra-sessions: In the past, selecting different sessions (netbook, gaming etc.) was installed by default. This is now an optional extra that can be    installed by those who want this added functionality.
* Lubuntu Mac images are [LTS](https://wiki.ubuntu.com/LTS) releases.

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

Lubuntu is a good operating system for many old computers, but not for all of them. Some computers have too little horsepower or memory. A rule of thumb is that the computer should not be more than 10 years old. The desktop image for lubuntu 15.10 requires a DVD / USB device to write it to, the alternate image remains CD sized for those who need this functionality.

### **Memory (RAM)**

For advanced internet services like Google+, Youtube, Google Docs and Facebook, your computer needs about 1 GB RAM.

For local programs like Libre Office and simple browsing habits, your computer needs about 512 MB RAM. See [minimal](https://help.ubuntu.com/community/Lubuntu/Documentation/MinimalInstall) for systems below that RAM.

### **Processor (CPU)**

The minimum specification for CPU is Pentium 4 or Pentium M or AMD K8.

Older processors are too slow and AMD K7 has problems with flash video.

### **Graphics chip / card**

Nvidia, AMD/ATI/Radeon and Intel work out of the box, or the system can be tweaked to work fairly easily. You can get help at the [Ubuntu Forums](https://ubuntuforums.org/). With such graphics, or if you don’t know, try the current Lubuntu version.

---

## Known Issues (Core)

### **Boot, installation and post-install**

* In Virtualbox, the installer currently has a bug where after the installation is complete, the installation medium will eject, but you will be unable to press ENTER to reboot. Powering off and back on should boot you into your installed system. This is being tracked in bug [1447038](https://bugs.launchpad.net/bugs/1447038)
* The amd64 (Intel x86 64bit) images specifically targeted at Apple hardware (amd64+mac) are no longer produced. Most Apple computers are now capable of booting the amd64 image directly using the EFI (not legacy) boot method so long as their firmware is up to date. If for some reason your hardware doesn’t boot properly using the amd64 image, make sure you don’t have a pending EFI update and if that still doesn’t ##work, then patch the 64-bit ISO using the software in [bug #1298894](https://bugs.launchpad.net/ubuntu-cdimage/+bug/1298894/comments/16) (tested working on Macbook 2,1). Alternatively, simply use the ##i386 (32bit) image instead.
* Due to changes in syslinux, it is not currently possible to use usb-creator from 14.04 and earlier releases to write USB images for 15.04; we believe that it is also not possible to use usb-creator from a 15.04 system to write USB images for earlier releases. For now the workaround is to use a matching release of Ubuntu to write the images, but we intend to issue updates soon to work around this incompatibility. [1325801](https://bugs.launchpad.net/bugs/1325801) (Lubuntu suggested workaround is to use [OBI](https://help.ubuntu.com/community/OBI) which is not affected by this problem).
* The Unetbootin versions in the Ubuntu repos are old ([1497604](https://bugs.launchpad.net/ubuntu/+source/unetbootin/+bug/1497604)) (Lubuntu suggested workaround is to use [OBI](https://help.ubuntu.com/community/OBI) which is not affected by this problem).
* Guided partitioning shortcut “max” gives minimum space instead [1163908](https://launchpad.net/bugs/1163908)

### **Upgrade**

* If several keyboard layouts are configured before upgrade, the wrong layout might be selected after upgrade ([1447157](https://bugs.launchpad.net/bugs/1447157)) Re-select the keyboard layout of your choice from the keyboard indicator or system-settings to make it the default. This setting will then persist upon reboot.\
* Celeron M computers can have trouble installing, [workaround exists](https://help.ubuntu.com/community/BootOptions/before--after).

---

## Ubuntu Release notes

* For a full list of issues and features common to Ubuntu, please refer to the [Ubuntu release notes](https://wiki.ubuntu.com/WilyWerewolf/ReleaseNotes).

---

## Known Issues (Lubuntu)

### **Desktop**

* run dialog opens on desktop with lxpanel config not current desktop ([1445818](https://bugs.launchpad.net/ubuntu/+source/lxpanel/+bug/1445818)).

### **Applications**

* lxpanel volume applet settings opens empty terminal window ([1434774](https://bugs.launchpad.net/ubuntu/+source/lxpanel/+bug/1434774) Workaround Exists)
* lubuntu-software-center only lists installed applications from alternate install ([1467517](https://bugs.launchpad.net/ubuntu/+source/lubuntu-software-center/+bug/1467517) Workaround Exists)
* Abiword language selector text cut off in abiword ([1484785](https://bugs.launchpad.net/ubuntu/+source/abiword/+bug/1484785))

### **Support**

* 9 months support
