# mnt and media

These two directories are both mount points, the places where extra filesystems get grafted onto the single tree that starts at [[root|/]]. They differ in who does the grafting.

`/media` is for removable storage that the system mounts automatically. Insert a USB drive or an SD card and your desktop environment typically creates something like `/media/dawid/MYUSB` and attaches it there without you lifting a finger.

`/mnt` is the manual, temporary spot reserved for the administrator. When you run a command such as `mount /dev/sdb1 /mnt` to inspect a disk by hand, this is the conventional place to do it.

Mounting is the act itself: it takes the filesystem on a [[dev|device]] like `/dev/sdb1` and makes its contents appear at a chosen directory. Until you mount it, the data on that disk is simply not part of the tree. Permanent mounts are usually not done here at all; they are declared in `/etc/fstab` so they happen automatically at boot, which is configuration that belongs to [[etc]].
