# Formatting-Floppy-Disks
Learn how to format floppy disks on Linux.

First, install the following packages on your distro.

## Install

### Fedora
```
sudo dnf install dosfstools
sudo dnf install ufiformat
```

### Debian/Ubuntu
```
sudo apt install dosfstools
sudo apt install ufiformat
```

## Finding Your Floppy Disk Reader Name
Use the following command to find your floppy disk reader name. Since I'm using a USB floppy disk reader, my floppy disk is going to be under the name "sdx". If I had an internal floppy drive, it would have been under "fdx".

In my case, since I only have one SSD on my laptop named "sda" for my whole operating system, my USB floppy disk reader will be "sdb".
```
lsblk
```

## Formatting
**NOTE: THIS WILL ERASE EVERYTHING ON YOUR FLOPPY DISK.**

Please replace XXX with your floppy disk reader name.

Most of the time, you will only have to use this command to format your floppy disk to FAT.
```
sudo mkfs.msdos /dev/XXX
```
If you are having issues where you get an error saying "mkfs.msdos: unable to discover size of dev/XXX", then you should use this command first and then format to FAT using mkfs. The first command does a low-level format, which helps set the floppy disk capacity.
```
sudo ufiformat /dev/XXX
```
```
sudo mkfs.msdos /dev/XXX
```

If you continue to have issues, it might be that your floppy disk is read-only due to the physical switch on the floppy. 

## Thank you
I wrote this Markdown file to remind myself how to format my floppy disks, since I still use them as secondary storage. I just like them since they are cool. Thank you for reading my document, and I hope you have a wonderful day.
