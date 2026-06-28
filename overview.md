# overview

A map of the whole vault. Every directory note hangs off [[root|/]], the apex of the tree, and the groups below sort them by what they are actually for rather than by alphabet.

## Where programs live

The executables and the libraries they load.

- [[bin]]: essential user commands available even in rescue mode.
- [[sbin]]: essential administrator commands, mostly needing root.
- [[lib]]: shared libraries and kernel modules backing the above.
- [[usr]]: the large secondary hierarchy holding packaged software.
- [[opt]]: self-contained third-party applications.

## Where data lives

Files owned by people and services.

- [[home]]: personal directories for ordinary users.
- [[root]]: the superuser's own home at `/root`.
- [[srv]]: data this machine serves to the outside.
- [[var]]: variable data such as logs, caches, and spools.

## Configuration and scratch

- [[etc]]: system-wide configuration as plain text.
- [[tmp]]: short-lived scratch space, often cleared on reboot.

## The kernel and hardware

These do not sit on disk; the kernel generates them live.

- [[dev]]: device files you read and write to reach hardware.
- [[proc]]: a window into processes and kernel tunables.
- [[sys]]: the structured view of devices, drivers, and buses.
- [[run]]: volatile runtime data for the current boot.

## Booting and attaching disks

- [[boot]]: the kernel, initramfs, and bootloader files.
- [[mnt and media]]: mount points where extra filesystems join the tree.

## How to read the graph

Start at [[root|/]] and follow the links outward. The clusters that form in Obsidian's graph view mirror these groups: the binary directories pull together through the usr merge, the virtual filesystems ([[proc]], [[sys]], [[dev]], [[run]]) cluster around the kernel, and [[etc]] threads through almost everything because nearly every directory is configured from there.
