# boot

`/boot` contains what the machine needs to start, before the main system is running. The two headline files are the kernel itself, usually named something like `vmlinuz-6.1.0`, and the `initramfs`, a small temporary root filesystem the kernel unpacks into memory so it can load the drivers required to reach the real disk.

The bootloader's files live here too. With GRUB you will find `/boot/grub/grub.cfg`, the menu that lets you pick a kernel. On UEFI systems there is usually a separate `/boot/efi` partition, formatted as FAT so the firmware can read it before any Linux driver exists.

Because the firmware reads this directory at power-on, `/boot` is often a small partition of its own, sometimes left unmounted during normal operation and attached only for a kernel update. Once the kernel is loaded it exposes its live state through [[proc]] and configures the rest of the tree from [[root|/]].
