---
aliases:
  - /dev
---

# dev

`/dev` is where "everything is a file" becomes literal. The entries here are device files: handles that let programs talk to hardware through ordinary read and write calls. `/dev/sda` is the first disk, `/dev/sda1` its first partition, `/dev/null` the bottomless sink that discards anything written to it.

Device files come in two flavours, visible in the first column of `ls -l`:

- Block devices (`b`) move data in fixed-size blocks and support random access, like disks and SSDs.
- Character devices (`c`) handle a stream one character at a time, like a keyboard, a serial port, or `/dev/random`.

`/dev` is not a normal directory on disk. It is managed at runtime by `udev`, which creates and removes nodes as hardware appears and disappears. Plug in a USB stick and a new `/dev/sdb` shows up within moments. You then make its filesystem usable by mounting it under [[mnt and media]]. The kernel's own running state, by contrast, is published through [[proc]] and `/sys`.
