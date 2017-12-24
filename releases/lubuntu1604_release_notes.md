# lubuntu 16.04 Release Notes


= Introduction =

These release notes for '''Ubuntu 16.04.3 LTS''' (Xenial Xerus) provide an overview of the release and document the known issues with Ubuntu 16.04 LTS and its flavours.  For details of the changes applied since 16.04, please see the [[XenialXerus/ReleaseNotes/ChangeSummary/16.04.3|16.04.3 change summary]].  The release notes for [[XenialXerus/ReleaseNotes/16.04|16.04]], [[XenialXerus/ReleaseNotes/16.04.1|16.04.1]], and [[XenialXerus/ReleaseNotes/16.04.2|16.04.2]] are available as well.

# Support lifespan
Ubuntu 16.04 LTS will be supported for 5 years for Ubuntu Desktop, Ubuntu Server, Ubuntu Core, and Ubuntu Kylin. All other flavours will be supported for 3 years.

# Official flavour release notes
Find the links to release notes for official flavours [[#Official_flavours|here]].


= Get Ubuntu 16.04.3 LTS =
== Download Ubuntu 16.04.3 LTS ==

Images can be downloaded from a location near you.
#### ''Note:'' The Ubuntu Desktop images are now bigger than a standard CD, and you should use a USB or DVD for installation.

You can download images from:

http://releases.ubuntu.com/16.04.3/ (Ubuntu Desktop and Server) 
http://cdimage.ubuntu.com/ubuntu/releases/16.04.3/release/ (Less Popular Ubuntu Images) 
http://cdimage.ubuntu.com/netboot/16.04.3/ (Ubuntu Netboot) 
http://cdimage.ubuntu.com/ubuntu-base/releases/16.04.3/release/ (Ubuntu Base) 
http://cdimage.ubuntu.com/kubuntu/releases/16.04.3/release/ (Kubuntu) 
http://cdimage.ubuntu.com/lubuntu/releases/16.04.3/release/ (Lubuntu) 
http://cdimage.ubuntu.com/ubuntustudio/releases/16.04.3/release/ (Ubuntu Studio) 
http://cdimage.ubuntu.com/ubuntu-gnome/releases/16.04.3/release/ (Ubuntu GNOME) 
http://cdimage.ubuntu.com/ubuntukylin/releases/16.04.3/release/ (Ubuntu Kylin) 
http://cdimage.ubuntu.com/ubuntu-mate/releases/16.04.3/release/ (Ubuntu MATE) 
http://cdimage.ubuntu.com/xubuntu/releases/16.04.3/release/ (Xubuntu) 
http://cdimage.ubuntu.com/mythbuntu/releases/16.04.3/release/ (Mythbuntu) 

##To install Ubuntu 15.04 for phones, follow the instructions found at [[Touch/Install]] to download and flash an image to your device.

== Upgrading from Ubuntu 14.04 LTS or 15.10 ==

To upgrade on a desktop system:
 * Open the "Software & Updates" Setting in System Settings.
 * Select the 3rd Tab called "Updates".
 * Set the "Notify me of a new Ubuntu version" dropdown menu to "For any new version" if you are using 15.10, set it to "long-term support versions" if you are using 14.04 LTS.
 * Press Alt+F2 and type in "update-manager" (without the quotes) into the command box.
 * Software Updater should open up and tell you: New distribution release '16.04 LTS' is available.
 * Click Upgrade and follow the on-screen instructions.

To upgrade on a server system:
 * Install the {{{update-manager-core}}} package if it is not already installed.
 * Make sure the /etc/update-manager/release-upgrades is set to normal if you are using 15.10, lts if you are using 14.04 LTS.
 * Launch the upgrade tool with the command {{{sudo do-release-upgrade}}}.
 * Follow the on-screen instructions.
Note that the server upgrade will use GNU screen and automatically re-attach in case of dropped connection problems.

There are no offline upgrade options for Ubuntu Desktop and Ubuntu Server. Please ensure you have network connectivity to one of the official mirrors or to a locally accessible mirror and follow the instructions above.


= New features in 16.04 LTS =

## Please see the [[https://blueprints.launchpad.net/ubuntu/xenial/+specs|Xenial blueprint list]] for details.

== Snap application format ==

Ubuntu 16.04 LTS introduces a new application format, the ‘snap’, which can be installed alongside traditional deb packages. These two packaging formats live quite comfortably next to one another and enable Ubuntu to maintain its existing processes for development and updates.
More information is available [[https://insights.ubuntu.com/2016/04/20/canonical-unveils-6th-lts-release-of-ubuntu-with-16-04/|here]].

== Updated Packages ==

As with every new release, packages--applications and software of all kinds--are being updated at a rapid pace. Many of these packages came from an automatic sync from [[http://www.debian.org|Debian]]'s unstable branch; others have been explicitly pulled in for Ubuntu 16.04.

For a list of all packages being accepted for Ubuntu 16.04, please subscribe to [[https://lists.ubuntu.com/mailman/listinfo/xenial-changes|xenial-changes]].

# Linux kernel 4.4
Ubuntu 16.04 LTS is based on the long-term supported Linux release series 4.4.

# Python 3
Python2 is not installed anymore by default on the server, cloud and the touch images, long live Python3!
Python3 itself has been upgraded to the 3.5 series.

If you have your own programs based on Python 2, fear not! Python 2 will continue to be available (as the python package) for the foreseeable future. However, to best support future versions of Ubuntu you should consider porting your code to Python 3. [[Python/3]] has some advice and resources on this.

# VIM defaults to python3
The default VIM package has been built against python3 instead of python2. This means plugins that require a python2 interpreter support from VIM will not work anymore.
For this case alternative VIM packages are available that still use python2, for example vim-gnome-py2.
They can be made the default via the alternatives mechanism:

 * `sudo update-alternatives --set vim /usr/bin/vim.gnome-py2`

# Golang 1.6
The golang toolchain was upgraded to the 1.6 series, and gccgo was upgraded to the GCC 6.1 release candidate 1. Thus the same level of standard library and compiler features are provided by both compilers on all fully supported architectures.

# OpenSSH 7.2p2

Recent OpenSSH releases disable several pieces of weak, legacy, and/or unsafe cryptography.  If you are upgrading a system remotely over SSH, you should check that you are not relying on these to ensure that you will retain access after the upgrade.

 * Support for the legacy SSH version 1 protocol is disabled by default at compile time.  Note that this also means that the `Cipher` keyword in [[http://manpages.ubuntu.com/manpages/xenial/en/man5/ssh_config.5.html|ssh_config(5)]] is effectively no longer usable; use `Ciphers` instead for protocol 2.  The [[apt:openssh-client-ssh1|openssh-client-ssh1]] package includes "ssh1", "scp1", and "ssh-keygen1" binaries which you can use if you have no alternative way to connect to an outdated SSH1-only server; please contact the server administrator or system vendor in such cases and ask them to upgrade.
 * Support for the 1024-bit `diffie-hellman-group1-sha1` key exchange is disabled by default at run-time.  It may be re-enabled using the [[http://www.openssh.com/legacy.html|upstream instructions]].
 * Support for `ssh-dss`, `ssh-dss-cert-*` host and user keys is disabled by default at run-time.  These may be re-enabled using the [[http://www.openssh.com/legacy.html|upstream instructions]].
 * Support for the legacy `v00` cert format has been removed.
 * Several ciphers are disabled by default in `ssh`: `blowfish-cbc`, `cast128-cbc`, all `arcfour` variants and the `rijndael-cbc` aliases for AES.
 * MD5-based and truncated HMAC algorithms are disabled by default in `ssh`.

# GNU toolchain

glibc was updated to the 2.23 release, binutils to the 2.26 release, and GCC to a recent snapshot from the GCC 5 branch (post GCC 5.3.0).

# Apt 1.2

Apt 1.2 includes the new privilege separation features introduced in Apt 1.1. Importantly, the unprivileged "_apt" user is now used when making outgoing network connections and parsing the results for the various apt transport methods (HTTP, HTTPS, FTP).

# Ubuntu for IBM LinuxONE and z Systems
Ubuntu 16.04 LTS includes a new port to 64-bit z/Architecture for IBM mainframe computers. This is a practically complete port of Ubuntu Server and Cloud with around 95% binary package availability. We are excited to enable !OpenStack software, Juju, MAAS, LXD, and much more on this platform.

For more information about this port see [[S390X]] page.

# Ubuntu Desktop

The general theme for 16.04 on the desktop is one of bug fixes and incremental quality improvements.

# General

 * GNOME is mostly upgraded to 3.18.  GLib upgraded to to 2.48 (corresponding to GNOME 3.20)
 * GNOME Software replaces Ubuntu Software Center.  This brings a faster store experience and moves our archive metadata in line with Debian.  It has been renamed "Ubuntu Software" to improve recognition for Ubuntu Software Center users.
 * All default applications and libraries ported to use !WebKit 2
 * GNOME Calendar is now included by default
 * Empathy and Brasero are removed from the default installation
 * Chromium upgraded to version 48
 * Firefox upgraded to version 45
 * Online searches in the dash are now disabled by default
 * Improved HiDPI support in the greeter
 * Added more supported languages by default [[https://lists.ubuntu.com/archives/ubuntu-devel/2015-December/039028.html|More info]]
 * Multiple bug fixes
## * HUD hotkey default binding changes from alt to alt-space.  The default window controls change to alt-super. This should help with issues around key interception in virtualized desktops and games.

# Unity & Compiz

 * Improved launcher integration with file manager and devices
 * Support for formatting removable devices from quicklist
 * Improved support for gtk applications using headerbars
 * Improvements to the switcher and spread backends
 * Activate app spread by Super+Ctrl+W
 * Unity control center option to always show menus
 * Improvements to GNOME key grabbing
 * New dash overlay scrollbars
 * Better Dash theming support
 * Support for scaling cursors in HiDPI environments
 * Show icons launching state in launcher when apps launched elsewhere
 * Launcher can be moved to the bottom

# LibreOffice

LibreOffice 5.1 brings a lot of improvements to the entire package.  For more information on these improvements please see the !LibreOffice release notes [[https://wiki.documentfoundation.org/ReleaseNotes/5.1|available here]].  You can see a video highlighting some of the new features [[https://www.youtube.com/watch?v=LrWPfWSuLSA&list=PL0pdzjvYW9RHSwdRnZfaxAWICrkBrQl7k|here]].

# General=
 * LibreOffice defaults to the Breeze theme in Ubuntu
 * Improvements in the Python scripting and language bindings [[http://conference.libreoffice.org/assets/Conference/Aarhus/Slides/MatthewFrancisPyUNO.pdf]]
 * Support for WebDAV via HTTPS

# Writer word processor=
 * Added support for whitespace hiding. A long standing feature request.
 * Mailmerge in Writer can use spreadsheets as a data source [[http://vmiklos.hu/blog/mail-merge-embedding.html]]
 * Spell check dialogue no longer auto closes

# Calc spreadsheets=
 * Exponential and power trend lines handle negative Y values
 * Performance improvements leveraging SSE3 for SUM functions
 * Added support for PNG export
 * Search for numbers as formatted/displayed

# Impress presentations=
 * Slide transitions use OpenGL 2.1+ and new transitions added
 * Keyboard shortcuts for navigation and sorting
 * Screensaver inhibiting for KDE, XFCE, Mate



== Ubuntu Server ==

# General

New in 16.04, the kernel crash dump mechanism now supports remote kernel crash dumps. It is now possible to send kernel crash dumps to a remote server using the SSH or NFS protocols. Details of the new functionality are available in the [[https://help.ubuntu.com/16.04/serverguide/kernel-crash-dump.html| Ubuntu Server Guide]].

Since the release of 16.04.2, the server ISOs are now larger than a standard 700MB CD. The increase in size is due to the ability to run the installer with the use of the [[Kernel/RollingLTSEnablementStack|Hardware Enablement (HWE) kernel]]. The HWE kernels enables newer platforms and components, which require functionality delivered in newer kernels, while allowing the continued use of an LTS release.

# OpenStack Mitaka

Ubuntu 16.04 includes  the latest !OpenStack release, Mitaka, including the following components:

 * !OpenStack Identity - Keystone
 * !OpenStack Imaging - Glance
 * !OpenStack Block Storage - Cinder
 * !OpenStack Compute - Nova
 * !OpenStack Networking - Neutron
 * !OpenStack Telemetry - Ceilometer and Aodh
 * !OpenStack Orchestration - Heat
 * !OpenStack Dashboard - Horizon
 * !OpenStack Object Storage - Swift
 * !OpenStack Database as a Service - Trove
 * !OpenStack DNS - Designate
 * !OpenStack Bare-metal - Ironic
 * !OpenStack Filesystem - Manila
 * !OpenStack Key Manager - Barbican

Please refer to the [[http://releases.openstack.org/mitaka/|OpenStack Mitaka release notes]] for full details of this release of !OpenStack.

!OpenStack Mitaka is also provided via the [[ServerTeam/CloudArchive|Ubuntu Cloud Archive]] for !OpenStack Mitaka for Ubuntu 14.04 LTS users.

Ubuntu 16.04 also includes the first GA release of of the Nova driver for LXD ('nova-lxd').

'''WARNING''': Upgrading an !OpenStack deployment is a non-trivial process and care should be taken to plan and test upgrade procedures which will be specific to each !OpenStack deployment.

Make sure you read the [[https://wiki.ubuntu.com/OpenStack/OpenStackCharms/ReleaseNotes1604|OpenStack Charm Release Notes]] for more information about how to deploy Ubuntu !OpenStack using Juju.

# libvirt 1.3.1

Libvirt has been updated to the 1.3.1 release.

# qemu 2.5

Qemu has been updated to the 2.5 release.

See http://wiki.qemu.org/ChangeLog/2.5 for details.

# Open vSwitch 2.5.0

Ubuntu 16.04 includes the latest release of Open vSwitch, 2.5.0.  This is also an LTS release of Open vSwitch.

Ubuntu 16.04 also includes support for Open vSwitch integrated with DPDK (Data Plane Development Kit) enabling fast packet processing through userspace usage of compatible networking cards - see the openvswitch-switch-dpdk package for more details.

# Ceph Jewel

Ubuntu 16.04 includes the latest release candidate (10.1.2) of the Ceph Jewel stable release; An update to the final release version will be delivered as an SRU to Ubuntu 16.04.

For full details on the Ceph Jewel release, please refer to the [[http://ceph.com/docs/master/release-notes/|upstream release notes]].

# Nginx

Ubuntu 16.04 includes version 1.9.15 of the Nginx web server, with an expectation to provide the next stable release of Nginx, 1.10.0, as an SRU after release (which will be virtually identical to 1.9.15). This version of Nginx also includes HTTP/2 support, which supersedes SPDY support previously provided in the Nginx packages.
# LXD 2.0
Ubuntu 16.04 LTS includes LXD, a new, lightweight, network-aware, container manager offering a VM-like experience built on top of Linux containers.

LXD comes pre-installed with all Ubuntu 16.04 server installations, including cloud images and can easily be installed on the Desktop version too. It can be used standalone through its simple command line client, through Juju to deploy your charms inside containers or with !OpenStack for large scale deployments.

All the LXC components - LXC, LXCFS and LXD - are at version 2.0 in Ubuntu 16.04 LTS.

Learn more about LXD here: http://www.ubuntu.com/cloud/lxd/ 
And discover all the LXD 2.0 features with: https://www.stgraber.org/2016/03/11/lxd-2-0-blog-post-series-012/

# docker 1.10
docker was upgraded to version 1.10. Note that this requires migration of existing images to a new format which will be performed on the first start of the service. This migration can take a long time and put a high load on the system; see https://docs.docker.com/engine/migration/ for more information.

# PHP 7.0

PHP was upgraded to 7.0. Note that this will require modifications to custom PHP extensions (https://wiki.php.net/phpng-upgrading) and may require modifications to PHP source code (http://php.net/manual/en/migration70.php).

 * NGINX and PHP 7.0
  Upgrading from a prior version of Ubuntu with PHP5 FPM configurations and NGINX will require a manual configuration change (details at: http://dark-net.net/nginx-http2-php7.0).

Most PHP-dependent packages were either rebuilt or upgraded for PHP7.0 support. Where that was not possible, packages may have been removed from the archive. There was one exception, Drupal7.
 * Drupal7 did not pass upstream testing with PHP7.0 as of the 16.04 release (https://www.drupal.org/node/2656548) and therefore the Ubuntu package was uninstallable. Before Ubuntu 16.04.2, Drupal7 was updated and is now installable (LP:1582340).

# MySQL 5.7

MySQL has been updated to 5.7. Some configuration directives have been changed or deprecated, so if you are upgrading from a previously customized configuration then you will need to update your customization appropriately. See [[https://bugs.launchpad.net/ubuntu/+source/mysql-5.7/+bug/1571865|bug 1571865]] for details.

Password behavior when the MySQL root password is empty has changed. Packaging now enables socket authentication when the MySQL root password is empty. This means that a non-root user can't log in as the MySQL root user with an empty password. For details, see the [[https://anonscm.debian.org/cgit/pkg-mysql/mysql-5.7.git/tree/debian/NEWS?id=1025a9fa9c6c112913c59138db49dbc94891d20f|NEWS]] file.

# Juju 2.0

Juju and Juju UI have been updated to 2.0beta4. The final Juju 2.0 release will come via an update post-release.  The package name is `juju-2.0`. Juju 1.25.5 is available in the `juju` package for existing production environments. Please read the [[https://jujucharms.com/docs/devel/juju-upgrade|upgrade documentation]] before moving to 2.0.

Juju now supports modeling workloads on AWS, Microsoft Azure, Google Cloud Engine, Rackspace, Joyent, LXD, MAAS, and manual deployments. 

 * The [[https://jujucharms.com/store|Juju Charm Store]] now has over 300 charms ready to deploy. Most of these workloads will deploy Trusty instances, but we expect 16.04 charms to start landing and being announced independent of Juju's release. 
 * [[https://jujucharms.com/docs/devel/temp-release-notes|Juju Core Release Notes]]
 * [[https://blog.jujugui.org/2016/04/15/juju-2-0-beta-4-now-with-embedded-gui/|Juju GUI Release Notes]]

= Known issues =

As is to be expected, with any release, there are some significant known bugs that users may run into with this release of Ubuntu 16.04.  The ones we know about at this point (and some of the workarounds), are documented here so you don't need to spend time reporting these bugs again:

## StartXenialReleaseBugs

== Boot, installation and post-install ==

# Installing Xen host in UEFI mode
It is currently impossible to boot a Xen hypervisor from grub in UEFI mode. However the package does not detect this and will set the default boot to Xen mode. So for any machine in UEFI mode, '''do not''' install the Xen hypervisor (or enable legacy mode first). Please see this [[https://bugs.launchpad.net/bugs/1520979|bug report]] for more information.

== Upgrade ==

# Kubuntu
'''WARNING''': LTS to LTS upgrade to Xerus is currently problematic and should not be attempted. Please install a fresh copy of 16.04 instead. To prevent messages about upgrading, change Prompt=lts to Prompt=normal or Prompt=never in the /etc/update-manager/release-upgrades file.

# OpenSSH

The default of the "UseDNS" configuration option has changed from yes to no. This may cause users who use the "from=" functionality in authorized_keys to limit ssh access by host to be locked out, which is especially troublesome if upgrading remotely. See [[https://bugs.launchpad.net/bugs/1588457|bug 1588457]].

# MySQL

Users with customised MySQL server configurations may hit a maintainer script error on upgrade due to changed configuration directives in MySQL 5.7. This will need to be fixed up manually. See the [[#MySQL_5.7|general MySQL update notes]] for details and instructions on fixing one common case of this.


== IBM LinuxONE and z Systems specific known issues ==

# Fully automated preseed install
Fully automated preseed installation is currently not possible with only DASD drives at the moment. For zfcp installation s390-zfcp/zfcp preseed key can be used. For more information please see [[https://bugs.launchpad.net/bugs/1572941|bug]] and [[https://bugs.launchpad.net/bugs/1564788|bug]].

# zfcpdump not available yet
zfcpdump kernel is not available yet, and will be made available as an SRU at a later date. Please see this [[https://bugs.launchpad.net/bugs/1565841|bug]] for more information.

# Install-time parameters are not propagated to the installed system
If installation is performed with special kernel parameters, e.g. cio_ignore, these are not propagated to the installed system. Please edit `/etc/zipl.conf` to apply these and re-run `sudo zipl` to update the IPL. Please see this [[https://bugs.launchpad.net/bugs/1571561|bug]] for more information.

# IPv6 with PCI/RoCE
The Linux kernel has an issue in its IPv6 stack with PCI/RoCE cards. IPv4 with PCI/RoCE cards is fully supported. The Linux kernel needs an upgrade to the first SRU kernel post-release for complete IPv6 PCI/RoCE support. Please see this [[https://bugs.launchpad.net/bugs/1572291|bug]] for more information.

# SCSI LUN detection issues
Usage of SCSI LUNs on a DS8870 Storage server with μCode Bundles 87.51.xx.0 (LMC 7.7.51.xx) via NPIV enabled zfcp adaptors causes detection issues. Please see this [[https://bugs.launchpad.net/bugs/1567602|bug]] for more information.

# z/EDC compression cards
There is a known issue with z/EDC compression cards. Please see this [[https://bugs.launchpad.net/bugs/1559194|bug]] for more information.

## Upgrade
## Power Management

== Desktop ==

# Unity 7
 * Sometimes Gtk application menus go missing [[https://bugs.launchpad.net/ubuntu/+source/unity/+bug/1532226]]. You can workaround this by launching this from a terminal or `Alt+F2` dash view:
  * `restart unity-panel-service`
# Ubuntu Software
  * Sometimes doesn't update apps to "Installed" after installation via search [[https://bugs.launchpad.net/ubuntu/+source/gnome-software/+bug/1551599]]
 * Does some time-consuming operations without any indicator [[https://bugs.launchpad.net/ubuntu/+source/gnome-software/+bug/1572606]]
 * Missing some details for apps that aren't installed [[https://bugs.launchpad.net/ubuntu/+source/gnome-software/+bug/1564621]] [[https://bugs.launchpad.net/ubuntu/+source/gnome-software/+bug/1571414]]
 * Removing apps leaves dependencies installed [[https://bugs.launchpad.net/ubuntu/+source/gnome-software/+bug/1552792]]
 * Doesn't recognize self-reviews [[https://bugs.launchpad.net/ubuntu/+source/gnome-software/+bug/1564209]]
 * Review stars aren't clickable [[https://bugs.launchpad.net/ubuntu/+source/gnome-software/+bug/1549555]]
 * Doesn't use full deb descriptions or translations [[https://bugs.launchpad.net/ubuntu/+source/gnome-software/+bug/1559338]]
 * Upgrades from previous versions can result in two Software Center icons in the launcher.  One for the old Ubuntu Software Center and one for the new Ubuntu Software application.  The Ubuntu Software Center icon can be removed if required.

== Server ==

# HTTP/2 support in Apache httpd

HTTP/2 support is [[https://httpd.apache.org/docs/2.4/mod/mod_http2.html|considered an experimental feature]] by the Apache httpd upstream project, and so we do not consider it suitable or maintainable for the 5 year supported period of this LTS release. Therefore HTTP/2 support is not available in our builds of Apache httpd.

We expect to issue stable release updates enabling HTTP/2 support after the Apache httpd upstream considers this support to be non-experimental, although this will depend on our assessment of the risk of regression to existing Xenial users at that time.

## Migration

== Graphics and Display ==

# fglrx

The fglrx driver is now deprecated in 16.04, and we recommend its open source alternatives (radeon and amdgpu). AMD put a lot of work into the drivers, and we backported kernel code from Linux 4.5 to provide a better experience.

When upgrading to Ubuntu 16.04 from a previous release, both the fglrx driver and the xorg.conf will be removed, so that the system is set to use either the amdgpu driver or the radeon driver (depending on the available hardware).

More information is available at [[https://tjaalton.wordpress.com/2016/03/11/no-catalystfglrx-video-driver-in-ubuntu-16-04/]]

# 6th gen Intel Core CPUs and llvmpipe software rasterizer

LLVM-3.8 enables AVX512 on all 6th generation Intel Core CPUs ("Skylake") when it should be enabled only on server CPU's. This causes the user session to fail to start when Mesa llvmpipe driver is used. This should happen only when the system has a separate GPU which isn't natively supported by open source drivers.

This bug will be handled in a post-release update. In order to install a machine suffering from this remember to boot directly to the installer instead of live-session which doesn't start, and select the option to "Download updates while installing" to make sure updated packages are installed before logging in for the first time. [[https://bugs.launchpad.net/ubuntu/+source/llvm-toolchain-3.8/+bug/1564156]]

## Networking

## == Kernel ==

= Official flavours =

The release notes for the official flavours can be found at the following links:
 * Kubuntu [[https://wiki.ubuntu.com/XenialXerus/ReleaseNotes/Kubuntu]]
 * Lubuntu [[https://wiki.ubuntu.com/XenialXerus/ReleaseNotes/Lubuntu]]
 * Ubuntu GNOME [[https://wiki.ubuntu.com/XenialXerus/ReleaseNotes/UbuntuGNOME]]
 * Ubuntu Kylin [[https://wiki.ubuntu.com/XenialXerus/ReleaseNotes/UbuntuKylin]]
 * Ubuntu Kylin 中文 [[https://wiki.ubuntu.com/XenialXerus/ReleaseNotes/UbuntuKylinChinese]]
 * Ubuntu Mate [[https://ubuntu-mate.org/blog/ubuntu-mate-xenial-final-release/]]
 * Ubuntu Studio [[https://wiki.ubuntu.com/XenialXerus/ReleaseNotes/UbuntuStudio]]
 * Xubuntu [[https://xubuntu.org/news/xubuntu-16-04-1-release]]
## * Edubuntu [[https://wiki.ubuntu.com/XenialXerus/ReleaseNotes/Edubuntu]]
## * Kubuntu [[https://wiki.ubuntu.com/XenialXerus/Beta2/Kubuntu]]
  * Mythbuntu [[http://www.mythbuntu.org/home/news/mythbuntu1604released]]
= More information =

# Reporting bugs

Your comments, bug reports, patches and suggestions will help fix bugs and improve the quality of future releases. Please [[http://help.ubuntu.com/community/ReportingBugs|report bugs using the tools provided]].

If you want to help out with bugs, the [[http://wiki.ubuntu.com/BugSquad|Bug Squad]] is always looking for help.

# Participate in Ubuntu

## These images were able to be made available to you thanks to the help of our [[https://wiki.ubuntu.com/SaucySalamander/TechnicalOverview/Beta1/Testers|QA Community]].

If you would like to help shape Ubuntu, take a look at the list of ways you can participate at

 http://www.ubuntu.com/community/get-involved

# More about Ubuntu

You can find out more about Ubuntu on the [[http://www.ubuntu.com|Ubuntu website]] and [[http://wiki.ubuntu.com|Ubuntu wiki]].

To sign up for future Ubuntu development announcements, please subscribe to Ubuntu's development announcement list at:

 http://lists.ubuntu.com/mailman/listinfo/ubuntu-devel-announce
