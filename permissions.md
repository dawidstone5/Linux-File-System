---
aliases:
  - file permissions
  - chmod
  - chown
---

# permissions

Every file carries permissions for three classes of people: the **user** who owns it, the **group** it belongs to, and **others**, meaning everyone else. Each class gets three bits: read (`r`), write (`w`), and execute (`x`). That is the `rwxr-xr-x` block you see in `ls -l`, stored in the file's [[inodes|inode]].

The bits mean slightly different things for directories. On a regular file, `x` lets you run it; on a directory, `x` lets you enter it and `r` lets you list its contents, so a directory you can enter but not read lets you reach a known filename inside without browsing.

People often set them by the octal shorthand, where read is 4, write is 2, execute is 1. So `chmod 644` gives the owner read and write, everyone else read only, while `755` adds execute for all, the usual setting for a program or a directory. Ownership is changed with `chown` and `chgrp`.

Beyond the basic nine there are special bits. The sticky bit on [[tmp]] stops users deleting each other's files in a shared directory. The setuid bit lets a program run with its owner's privileges rather than the caller's, which is how an ordinary user can change their own password through a root-owned binary. System-wide account and group definitions that back all of this live in [[etc]].
