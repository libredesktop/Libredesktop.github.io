# Installation Guide

## Step 0: Pre-installation

Before installing Lubuntu, be sure to disable Secure Boot and Fast Boot in BIOS, if the options exist. Some distros can work with Secure Boot enabled, but we still recommend disabling it for various reasons.

If you have Windows installed and wish to dual-boot, do the following: go to Power Options -> Choose what the power buttons do -> Change settings that are currently unavailable -> Disable “Fast startup (recommended)” and Hibernation, update Windows, restart, shrink Windows from within Windows using Disk Management to create “Unallocated Space” (preferably, at least 60 GB) for Linux, update Windows, restart.

## Step 1: Creating Installation Media

After you’ve downloaded the ISO file. You will either need to burn this image to a DVD or you will need to put it on an 4+ GB flash drive. You can use the included software in your OS to burn it to a DVD.

Alternatively, you can put it on a flash drive. If you are creating the installer from Windows, you’ll need to download a tool called [Rufus](https://rufus.akeo.ie/). To put it on a flash drive if you are creating the installer from Mac or Linux, you can use the built-in tool.

### Windows:

1. Download and run Rufus.
2. Near the bottom, select “ISO Image” and then browse for the ISO image.
3. Select which flash drive you want to put the installer on.
4. Click “Start” and wait for it to finish.

### MacOS:

Visit this [link](https://tutorials.ubuntu.com/tutorial/tutorial-create-a-usb-stick-on-macos)

### Linux:

You can use inbuilt Startup Disk Creator to do it.

## Step 2: The Actual Installation

Reboot the computer and select the flash drive or DVD. If you disabled Secure Boot and Fast Boot in BIOS (if applicable), this should be easy.

When the image boots, select “Try”. You can proceed with the installation from “Try”, too, but the “Try” just loads up the live session all the way, which allows you to run programs other than the installer just in case we need to do other things. From the “Try” session, you should connect to WiFi if applicable, as WiFi is one of the most likely things to have problems working (it still works >95% of the time out of the box) so it’s good to check if it works from here.

If you have a single drive in your system and want the easy option, then you can select one of the easy installation options, such as “Install alongside [existing OS here]” or “Erase disk and install”. However, if you have multiple disks or want to have more control over configuring your partitions, click “Something Else” (fairly advanced).

### Easy Installation Options

(for single disks and simple configurations)

Ensure you can read your disk fine, if it have data on it. You can mount your disk by clicking the desktop icon.

Run the installer, select your language, and check both of the two boxes. Then, select either “Install alongside [existing OS here]” or “Erase disk and install”.

### “Something Else”

(fairly advanced, for multi-disk systems or custom partition setups)

1. Open GParted, and perform the next for all empty disks.
2. Select “Device” -> “Create Partition Table…”
 1. UEFI systems
    1. Set the partition table type to `gpt` (typically capitalized: “GPT”).
    2. Before creating any partitions, note that on GPT disks, you should ALWAYS use **Primary** rather than Logical or Extended partitions.
    3. Create an EFI System Partition, about 1 GB, create as “Primary Partition”, file system `fat32`, with a name of “EFI System Partition”.
    4. Always after making changes to partitions, you have to click the green check mark to apply the changes.
    5. Right-click and select “Manage Flags”, and enable the `boot` flag for your EFI system partition (the esp flag should auto-enable when you do this, if not, manually enable that too).
 2. Legacy BIOS systems
    1. Set the partition table type to `msdos` (also known as MBR).
    2. Unlike with UEFI, no special partitions need to be created in GParted. You’re done.
3. If you have any other empty disks, give them the correct type of partition tables as well, however, you don’t need EFI System Partitions for non-bootable drives.
4. Close GParted if nothing else needs to be done.

### Once you’ve prepared your disks

1. Open the installer, select your language, and then check both of the two boxes.
2. The installer will present you with a choice of where you want to install the OS to.
3. On your primary drive, select the “free space” and press `+` to create a partition.
4. Make it approximately 40 GB, type as “Primary”, use as “ext4 journaling file system”, and mount point as /. This is where the OS and programs will be located.
5. Create another partition which fills the rest of the space, type as “Primary”, use as “ext4 journaling file system”, and mount point as /home. This is where your files are stored, such as what you put on your desktop and downloads folders, your configuration files, and everything else in your home folder (also known as `~` in Terminal-speak).
6. If you have multiple drives, you should also create partition(s) on them if they are empty (same settings, “Primary”, use as “ext4 journaling file system”, and perhaps mount it as `/storage`).
7. Before clicking “Install Now”, ensure that the “Device for boot loader installation” is set to your primary drive (`/dev/sd[letter]` with **NO NUMBER**).

### The Rest of the Installation

The rest of the installation should be mostly self-explanatory. You have to enter the username and password that you want, choose your computer’s name, set your timezone, etc.

Once the installation has finished, it will ask you to reboot. Do it, and log in.

If you are dual-booting, you should also make note of GRUB, the tool that allows you to select which OS you want when your computer starts up.

Source: /r/TechSupport.org, Click [here](https://rtechsupport.org/kb/linux-installation/)
