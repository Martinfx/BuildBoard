# Embedded Freebsd with zfs

This is simple creation scripts of image.
It creates ZFS root and set up root ssh login using ssh key.

## Requirements

 - Freebsd system with ZFS pool
 - microSD card >=4GB
 - Some board

## Image Creation

```
$ fetch https://raw.githubusercontent.com/MartinFx/BuildBoard/main/create_img.sh
$ chmod +x create_img.sh
$ ./create_img.sh
```

You may edit the variables at the beginning of `create_img.sh` to set up things like which dataset of your ZFS will be used.

Mainly is suggested to change the PUB_KEY variable with your ssh pub key

## Image upload and start

Copy the image to the sdcard, use the correct path to the image and the correct mmc device.

```
dd if=/rpool/nanopi/Orangepi-13.0.img of=/dev/mmcXXX bs=1M
```

Then you can plug the SD card to NanoPI and boot it.
It is adwised to have the LAN cable connected.

You may use serial cable, but it is not needed.
If you do, the speed is 1500000.

Example connecting from my linux laptop:
```
$ screen /dev/ttyUSB0 1500000
```
