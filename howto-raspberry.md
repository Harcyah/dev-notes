# How to ... Raspberry !

## Get hardware details

```
$ cat /proc/cpuinfo

processor       : 0
model name      : ARMv6-compatible processor rev 7 (v6l)
BogoMIPS        : 2.00
Features        : half thumb fastmult vfp edsp java tls
CPU implementer : 0x41
CPU architecture: 7
CPU variant     : 0x0
CPU part        : 0xb76
CPU revision    : 7

Hardware        : BCM2708
Revision        : 000e
Serial          : 00000000f044c0ed
```

=> "Model B Revision 2.0 512MB, (Sony)"

## GPIO

http://pi4j.com/pins/model-b-rev2.html


## Format USB

```
sudo parted /dev/sda mklabel msdos
sudo parted -a none /dev/sda mkpart primary fat32 0 8061
sudo mkfs.vfat -n "cruizer0" /dev/sda1
```
