---
aliases:
  - filesystem types
  - ext4
  - xfs
  - btrfs
  - mkfs
  - fsck
---

# filesystem types

A "filesystem" in this sense is the on-disk format that decides how bytes turn into named files, where [[inodes|inodes]] sit, and how free space is tracked. Linux supports many, and the choice is a real engineering trade-off.

- **ext4** is the long-standing default. It is mature, well understood, and a safe pick for almost anything, using journaling to recover cleanly after a crash.
- **XFS** was built for scale and parallel throughput, which is why it tends to win with very large files and many simultaneous writers. Red Hat ships it as the server default.
- **Btrfs** is the modern copy-on-write design, bringing snapshots, checksums that catch silent corruption, and built-in volume management. The price is more moving parts to understand.
- **FAT32 and NTFS** are not native Linux formats at all. You meet them for compatibility, on a USB stick or a Windows partition shared across a dual boot.

You lay a fresh filesystem onto a partition with `mkfs`, for example `mkfs.ext4 /dev/sdb1`, then make it usable by mounting it under [[mnt and media]]. When one is damaged, `fsck` walks its structures and reconciles the [[inodes|inodes]] against their directory entries. Which partition holds which type, and where each gets mounted, is recorded in `/etc/fstab` over in [[etc]]. Note that the virtual filesystems [[proc]], [[sys]], and [[run]] use none of this; they are generated in memory and never formatted.
