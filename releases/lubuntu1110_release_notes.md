# lubuntu 11.10 (OneiricOcelot) Release Notes

## Improvements since Lubuntu 11.04

   - ISOs are now build with Ubuntu official build system.
   - Alternate ISOs are available.
   - Many updates from LXDE (most components had official releases).
   - Build with recommended packages by default.
   - Use recommends instead of depends for most of components of lubuntu-desktop meta-package.
   - Register correctly LXDE as a desktop environment by xdg tools.
   - Switch to xfce4-power-manager for power management.
   - Add a microblog client : pidgin-microblog.
   - New theme made by Rafael Laguna. 

## System Requirements

The minimum memory requirement for running Lubuntu 11.10 is 128 MB of memory. Note that some of your system's memory may be unavailable due to being used by the graphics card.

To use the graphical installer from the Live-CD (Desktop ISO), you need at least 256 MB of memory to use the "Install Lubuntu" entry when you boot from the Live-CD. It's recommended to have 384 MB at least to install using "Try Lubuntu without installing" entry on the boot menu. You maybe able to use the previous mentioned features with less memory (less than 256 MB) but the overall response will be very slow.

Systems with less memory need to use alternate ISO, or perform a minimal installation (see [Minimal Install](https://wiki.ubuntu.com/Lubuntu/DocumentationHelp/MinimalInstall)).

Ubuntu (and so Lubuntu) dropped the support for the following CPUs:

   - VIA C3
   - AMD K6
   - National Semiconductor
   - AMD Geode 

You will not be able to upgrade or to install if you're using this CPU model. The team are going to support [10.04](https://wiki.ubuntu.com/Lubuntu/DocumentationHelp#10.04) longer than a standard version. 

## Lubuntu notes

### Desktop ISO boot to a terminal prompt

In some cases, Lubuntu desktop ISO boots to a terminal prompt instead of the desktop session when "Try Lubuntu without installing" is chosen. You can manually start the session by typing "sudo start lxdm" ([854837](https://bugs.launchpad.net/bugs/854837)). Or you can choose "Install Lubuntu" and once the installer starts, click "Quit" then "Quit" and you'll get the live desktop.

For more information, please see [this link](http://ubuntuforums.org/showpost.php?p=11398602&postcount=35)

### Needed installation size for graphical installation

The graphical installer will not continue if you have less that 4.3 GB available for installation. However, you can install Lubuntu using the alternate ISO or the [minimal installation instructions](https://wiki.ubuntu.com/Lubuntu/DocumentationHelp/MinimalInstall) with less than 4 GB available. See also [819538](https://bugs.launchpad.net/bugs/819538)

### Keyboard layout not saved

The keyboard layout can't be saved using LXKeymap. To change permanently your keyboard layout, please run "sudo dpkg-reconfigure keyboard-configuration" ([729880](https://bugs.launchpad.net/bugs/729880)).

### Desktop icons not updated during persistent session

On persistent mode of the desktop ISO, items created on the desktop are not displayed until next reboot. ([837470](https://bugs.launchpad.net/bugs/837470))

### Quick search Synaptic

The quick search feature in Synaptic is disabled by default, due to hanging on some systems with it enabled. However if you are confident that this won't happen to you, it is easily enabled. Just open a [LXTerminal](https://wiki.ubuntu.com/Lubuntu/DocumentationHelp/LXTerminal) session and enter the following command:

`sudo apt-get install apt-xapian-index`

It has an additional dependency it wants to install to function properly. After installation it will index the repositories, which will take few minutes the first time. After this small venture to the terminal it should work properly again.

Another option is to install it with Synaptic itself, but don't be surprised it the quick search option remains grayed out / not visible at all until after a shutdown of synaptic. To install it with synaptic you only need to search for apt-xapian-index, mark it for installation and apply. 
