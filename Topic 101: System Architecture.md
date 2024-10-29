# 101.1 Determine and configure hardware settings

**$ lspci:** Shows all devices currently connected to the PCI (Peripheral Component Interconnect) bus

**$ lspci -s 04:02.0 -v:** The command lspci shows more details about a specific device if its address is given with option -s, accompanied by the option -v

**$ lspci -s 01:00.0 -k:** Verify which kernel module is in use for the specified device is provided by the option -k, available in more recent versions of lspci

**$ lsusb:** Lists USB (Universal Serial Bus) devices currently connected to the machine

**$ lsusb -v -d 1781:0c9f:** As with lspci, option -v displays more detailed output. A specific device can be selected for inspection by providing its ID to the option -d.

**$ lsusb -t:** Shows the current USB device mappings as a hierarchical tree:

**$ lsusb -s 01:20:** To verify which device is using the module btusb, present in the previous listing, both Bus and Dev numbers should be given to the -s option of the lsusb command

**kmod package:** A set of tools to handle common tasks with Linux kernel modules like insert, remove, list, check properties, resolve dependencies and aliases. The lsmod command, for example, shows all currently loaded modules.

**$ lsmod:** Shows all currently loaded modules. It is common to have a large set of loaded kernel modules in a standard Linux system at any time.</br> The output of command lsmod is divided into three columns: ***Module:*** Module name. ***Size:*** Amount of RAM occupied by the module, in bytes.
***Used by:*** Depending modules.

**$ modeprobe -r <module>:** To unload a module and its related modules, as long as they are not being used by a running process, command modprobe -r should be used.</br> For example: ***$ modprobe -r snd-hda-intel:*** Unload module snd-hda-intel (the module for a HDA Intel audio device) and other modules related to the sound
system

**$ modinfo -p <module>:** shows a description, the file, the author, the license, the identification, the dependencies and the available parameters for the given module: ***$ modinfo -p nouveau:*** Shows a description of the nouveau module

