Lubuntu is a good operating system for many old computers, but not for all of them. Some computers have too little horsepower or memory. A rule of thumb is that the computer should not be more than 10 years old.

If you have an older or less powerful system, and you are ready for advanced methods, read the tips at this page. 

##	Memory(RAM)

###	Normal usage

If you plan to use advanced internet services like Google+, Youtube, Google Docs and Facebook, your computer needs at least 1 GB RAM, but 2 GB RAM makes the computer work better.

If you plan to use local programs like Libre Office (for word processing,spreadsheet calculations and presentations) and Thunderbird for email, and seldom browse to web pages with a lot of graphics and animations, your computer needs 512 MB RAM, but 768 MB or 1 GB RAM makes it work significantly better. 


###	Advanced usage with low RAM

We have done many tests and we've found out that Lubuntu Core Trusty can be installed on a Pentium II or Celeron system with 128 MB RAM, but such a system would not perform well enough for daily use. Standard Lubuntu needs at the very least 192 MB RAM, but will not perform well enough for daily use.

With 256MB - 384MB of RAM, the performance will be better and the system will be more usable.

With 512MB of RAM or more, you need not worry much, it is within normal usage

Browsers are notorious for using up RAM, you may find that Chromium and / or Firefox need more resources than your computer has. There is a minimal browser called xombrero which continues to be built by a fellow lubunteer. It is not available from the Ubuntu Universe repository' (For 10.04, it was called xxxterm and the old version is in repository). 

##	Processor(CPU)

###	Normal usage

The minimum specification for CPU is Pentium 4 or Pentium M or AMD K8.

Older processors are too slow and AMD K7 has problems with flash video.

Pentium M and Celeron M

Xubuntu 12.04 LTS (the original, before the point releases) has a non-pae kernel and works out of the box.

Systems based on Ubuntu 12.04.5 LTS 'Precise' can be installed in Pentium M and Celeron M computers using fake-PAE. This can be done using the One Button Installer or Lubuntu-fake-PAE.

Lubuntu 14.04 LTS 'Trusty' and newer versions of Lubuntu can use the boot option forcepae and can be installed using the standard installers.

After selecting language you arrive at the main menu of the installer. Click on F6

At the boot menu screen the options are

1.    Try Lubuntu without installing (in the desktop installer but not in the alternate installer]
2.    Install
3.    ... 

With the Install choice high-lighted press F6. (This option needs less RAM than installing from 'Try Lubuntu')

A menu with a number of options appears. The option 'forcepae' is not there, so press Escape to close the list.

Now a string of options is visible, often with 'quiet' or 'quiet splash --' at the end. Add 'forcepae' to the string before and after the two dashes.

In newer versions of Lubuntu, we should enter forcepae twice

... quiet splash forcepae -- forcepae

according to this link: BootOptions/before--after

Press return, and the installation begins.

###	Advance usage with old processors

It is possible to run Lubuntu Core and standard Lubuntu with Pentium II, Pentium III or Celeron processors and contemporary AMD processors, but the computer will be slow, and some tasks may not work.

On the other hand, such computers will probably work well enough in text mode for example as file server in a local network.

VIA C7 might run with Xubuntu 12.04 LTS or Bento, Bodhi, LXLE. 


### Graphics chip / card

Nvidia, AMD/ATI/Radeon and Intel work out of the box, or the system can be tweaked to work fairly easily. You can get help at the Ubuntu Forums. With such graphics, or if you don't know, try the current Lubuntu version.

###	Nvidia or AMD/ATI/Radeon

A good start is to use the boot option nomodeset, if it does not work out of the box. Nvidia and AMD/ATI/Radeon might work better with a proprietary driver, that can be installed after booting with nomodeset. 

### Old Intel graphics

Old Intel graphics may need UXA acceleration instead of the default

There was this helpful bug report on file at [http://bugs.launchpad.net/ubuntu/+source/linux/+bug/1178982](http://bugs.launchpad.net/ubuntu/+source/linux/+bug/1178982)

The work-around (Comment #1) was to change the Xorg acceleration method to UXA.

Work-around:

Edit (or create) /etc/X11/xorg.conf as follows: (there should be a tab before each line except the first and the last).

Section "Device"
        Identifier "Intel Graphics"
        Driver "intel"
        Option "AccelMethod" "uxa"
EndSection

Restart X (reboot, restart your display manager, whatever). Colors are back to the way they used to be and flash works.

### SIS graphics

SIS graphics should be run with flavours or re-spins of Ubuntu 12.04 LTS, for example Bento, Bodhi, LXLE. 

##	Installers

###	Normal usage

The desktop installer works in most cases. If you have problems, for example with the graphics, try the alternate installer.

###	Advanced usage

The desktop installer needs more RAM than the other alternatives. So you should try other installers, if you have low RAM.

##	Test results

Test results concerning minimum and recommended RAM to install Lubuntu 14.04 LTS, 'Trusty'

The test were performed with the boot option 'mem' in the following computer

[http://www.toshiba.se/laptops/satellite-pro/c850/satellite-pro-c850-19w/](http://www.toshiba.se/laptops/satellite-pro/c850/satellite-pro-c850-19w/)

('effective' is what is reported by 'free -m' as total memory)

###	Erase disk and install (with swap partition on the HDD)

Lubuntu Trusty desktop 32-bit beta2
mem=256M (effective 241M) OK
mem=224M (effective 210M) heavy swapping to zram and disk, but OK
mem=192M failure

###	Erase disk and install (without swap partition on the HDD)

Lubuntu Trusty desktop 32-bit beta2
mem=256M (effective 241M) OK
mem=224M (effective 210M) heavy swapping to zram, but OK
mem=192M failure

Lubuntu Trusty alternate 32-bit beta2
mem=192M (effective 178M) OK
mem=176M (effective 162M) OK
mem=160M failure

###	Summary

Absolute minimun RAM for the standard installers

1.    Lubuntu Trusty desktop 32-bit: 224 MB
2.    Lubuntu Trusty alternate 32-bit: 176 MB 

More memory is necessary for more advanced install alternatives, for example dual boot using 'Something else' at the partitioning window.

Recommended minimum RAM for the standard installers

1.    Lubuntu Trusty desktop 32-bit: 384 MB
2.    Lubuntu Trusty alternate 32-bit: 256 MB 

##	Alternative installers

##	Ubuntu mini.iso

The Ubuntu mini.iso alias Minimal Install alias Netboot Install is a very small iso file, that will fetch the main part of the installed system via the internet. This installer is very flexible and can be used to install all flavours of Ubuntu (including Lubuntu Core which is smaller than standard Lubuntu). Contrary to the full desktop flavours of Ubuntu the minimal system and the server will be installed with a non-portable network connection unless you tweak the system according to 'Unmanaged Wired Network' in the following link.

[https://help.ubuntu.com/community/Lubuntu/Documentation/MinimalInstall](https://help.ubuntu.com/community/Lubuntu/Documentation/MinimalInstall)

The Ubuntu mini.iso is a good starting point if you want to install a customized system, where you install only the software packages you intend to use. But it is more complicated than the standard desktop and alternate installers. Due to the increase of the linux kernel, the RAM size necessary has increased in 14.04 LTS compared to 12.04 LTS. Do not expect to succeed with less than 128 MB RAM. You may need as 'much' as 160 MB to install Ubuntu server 14.04 LTS.

###	Debootstrap

Adapted from the official Ubuntu guide.

1.    Boot off of a Ubuntu or Ubuntu flavor's live image, ensuring it is the same release you plan on installing, for example, use a 16.04 image if you plan on installing Xenial.
    a.    Distributions based off of Ubuntu or an Ubuntu flavor such as Linux Mint should be fine, as long as it uses packages directly from the Ubuntu repositories. 
2.    Partition your hard drive how you would like it, mounting the root partition under /mnt. If applicable, mount additional partitions under /mnt (if you use /home on a separate partition for example).

3.    Ensure the debootstrap program is installed by typing the following in a terminal:

    `sudo apt update && sudo apt -y install debootstrap`

4.    Run the following command to install the base system:

    `sudo debootstrap --arch ARCH RELEASE /mnt/`

    a.    Be sure to replace ARCH with an architecture compatible with your CPU, such as amd64 or i386.
    b.    Be sure to replace RELEASE with a release such as xenial. 

5.    Run the following to chroot into your newly-installed system:

    `sudo chroot /mnt/`

6.    Mount proc and sys:

    `mount -t proc proc /proc`
    `mount -t sysfs sysfs /sys`

7.    Make generic device files:

    `cd /dev && MAKEDEV generic`

8.    Edit your fstab file:

    `editor /etc/fstab`

    a.    In a different terminal window, run sudo blkid to get the UUID of your partitions. This is preferred over using partition names. Be sure to remove the quotes around the UUID. This is an example fstab file that has the home partition mounted separately:

    b.    UUID=XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX       /       ext4    defaults        0       1
        UUID=XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX       /home   ext4    defaults        0       1

        Be sure to replace the UUIDs with appropriate partition UUIDs for your system. Please read some more about using fstab. Also, if your system has more than 4 gigabytes of RAM, you may benefit from mounting /tmp as a tmpfs. Read Dustin Kirkland's analysis on this if this interests you. 

9.    Mount all the partitions you just specified in your fstab file just to be sure:

    `mount --all`

10.   Set the time zone:

    `dpkg-reconfigure tzdata`

11.   Configure networking:

    `editor /etc/network/interfaces`

    a.    Adapt the following and put it in that file:

        ######################################################################
        # /etc/network/interfaces -- configuration file for ifup(8), ifdown(8)
        # See the interfaces(5) manpage for information on what options are
        # available.
        ######################################################################

        # We always want the loopback interface.
        #
        auto lo
        iface lo inet loopback

        # To use dhcp:
        #
        # auto eth0
        # iface eth0 inet dhcp

        # An example static IP setup: (broadcast and gateway are optional)
        #
        # auto eth0
        # iface eth0 inet static
        #     address 192.168.0.42
        #     network 192.168.0.0
        #     netmask 255.255.255.0
        #     broadcast 192.168.0.255
        #     gateway 192.168.0.1

12.   Add your nameservers:

    `editor /etc/resolv.conf`

    a.    Example:

        `search hqdom.local`
        `nameserver 10.1.1.36`
        `nameserver 192.168.9.100`

13.    Enter your system hostname, remembering to replace HOSTNAME with the host name you wish to use:

    `echo HOSTNAME > /etc/hostname`

14.   Create your /etc/hosts file, insert the following remembering to replace HOSTNAME with the host name you specified in the last step:

    `127.0.0.1 localhost`
    `127.0.1.1 HOSTNAME`

    # The following lines are desirable for IPv6 capable hosts
    ::1     ip6-localhost ip6-loopback
    fe00::0 ip6-localnet
    ff00::0 ip6-mcastprefix
    ff02::1 ip6-allnodes
    ff02::2 ip6-allrouters
    ff02::3 ip6-allhosts

15.   Configure apt, remembering to replace RELEASE with the release name you specified in step 4, by putting the below in /etc/apt/sources.list:

    `deb http://archive.ubuntu.com/ubuntu/ RELEASE main restricted universe multiverse`
    `deb-src http://archive.ubuntu.com/ubuntu/ RELEASE main restricted universe multiverse``

    `deb http://archive.ubuntu.com/ubuntu/ RELEASE-updates main restricted universe multiverse`
    `deb-src http://archive.ubuntu.com/ubuntu/ RELEASE-updates main restricted universe multiverse`

    `deb http://archive.ubuntu.com/ubuntu/ RELEASE-backports main restricted universe multiverse`
    `deb-src http://archive.ubuntu.com/ubuntu/ RELEASE-backports main restricted universe multiverse`

    `deb http://security.ubuntu.com/ubuntu RELEASE-security main restricted universe multiverse`
    `deb-src http://security.ubuntu.com/ubuntu RELEASE-security main restricted universe multiverse`

    a.    If you are using the development release:

        `deb http://archive.ubuntu.com/ubuntu/ RELEASE main restricted universe multiverse`
        `deb-src http://archive.ubuntu.com/ubuntu/ RELEASE main restricted universe multiverse`

    b.    If you plan on staying on the development release:

        `deb http://archive.ubuntu.com/ubuntu/ devel main restricted universe multiverse`
        `deb-src http://archive.ubuntu.com/ubuntu/ devel main restricted universe multiverse`

16.    Run the following to update the repositories and make sure the system is fully updated:

    `apt update && apt -y dist-upgrade`

17.    Create the /etc/kernel-img.conf file with the following contents:

    `do_symlinks = yes`
    `relative_links = yes`
    `do_bootloader = no`
    `do_bootfloppy = no`
    `do_initrd = yes`
    `link_in_boot = no`
    `postinst_hook = update-grub`
    `postrm_hook = update-grub`

18.   Install the kernel and bootloader:

    `apt install linux-generic`

19.   Add a user, replacing USER with your desired username:

    `adduser USER && adduser USER sudo`

20.   You can now install the Lubuntu desktop.

    a.    If you wish to install LXQt, run: apt install software-properties-common && add-apt-repository ppa:tsimonq2/lxqt-meta && apt update && apt install lxqt-metapackage

    b.    If you wish to install stock Lubuntu, run: apt update && apt install lubuntu-desktop 
21.   (optional) using apt, install any other application you may want to use on your system.

22.   Use Ctrl + D to exit and reboot into your new system! Smile :) 

###	The One Button Installer can install systems with 128 MB RAM

The One Button Installer can install dual boot systems.

Lubuntu 13.10 'Saucy' can be installed with the One Button Installer in Pentium M and Celeron M computers using fake-PAE. (Lubuntu 14.04 LTS 'Trusty' can use the boot option forcepae and can be installed using the standard installers.)

[https://help.ubuntu.com/community/OBI](https://help.ubuntu.com/community/OBI)

The 9w installer can install systems with 80 MB RAM

###	The 9w installer can install systems with 80 MB RAM, but Lubuntu Core Trusty needs 128 MB RAM to run and at least 256 MB RAM to be really useful.

See this wiki page

[https://help.ubuntu.com/community/9w](https://help.ubuntu.com/community/9w)

and this page, where you can download the 9w iso files

[http://phillw.net/isos/linux-tools/9w/](http://phillw.net/isos/linux-tools/9w/)

Computers with less memory than 256 MB of RAM can be used in text mode (or maybe in graphics mode with some other really small linux distro).

See posts #88, 89 and the following posts in this thread about 9w.

[http://ubuntuforums.org/showthread.php?t=2209683&page=5&p=12957586#post12957586](http://ubuntuforums.org/showthread.php?t=2209683&page=5&p=12957586#post12957586)

[http://ubuntuforums.org/showthread.php?t=2209683&page=6&p=12957950#post12957950](http://ubuntuforums.org/showthread.php?t=2209683&page=6&p=12957950#post12957950)

[http://ubuntuforums.org/showthread.php?t=2209683&page=8&p=12962755#post12962755](http://ubuntuforums.org/showthread.php?t=2209683&page=8&p=12962755#post12962755)

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/80x15.png" /></a> This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons License</a>.
