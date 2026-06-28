---
aliases:
  - /sbin
---

# sbin

`/sbin` is the administrator's toolbox. The "s" stands for system: these are the binaries used to set up, repair, and maintain the machine rather than to do everyday work. `fsck` to check a filesystem, `mkfs` to create one, `mount`, `reboot`, `ip`, and `fdisk` all live here.

Like [[bin]], `/sbin` holds tools considered essential at boot, which is why it sits beside [[root|/]] and not under [[usr]]. The split from `/bin` is about audience, not permission magic: the commands here generally need root privileges to do anything useful, so they are kept apart from the ones every user runs.

The companion directory for non-essential admin tools is `/usr/sbin` within [[usr]]. As with the other binary directories, the usr merge on modern systems turns `/sbin` into a symlink to `/usr/sbin`, collapsing the historical distinction while keeping the familiar name.
