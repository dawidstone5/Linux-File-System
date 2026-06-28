---
aliases:
  - hard link
  - soft link
  - symbolic link
  - symlink
---

# links

A link is a second name for a file, and Linux offers two kinds that behave very differently.

A **hard link** is another directory entry pointing at the same [[inodes|inode]]. Both names are equal; neither is the "original". The inode keeps a link count, and the data survives until that count hits zero, so deleting one name simply decrements the count and leaves the other working. The catch is that a hard link cannot cross a filesystem boundary, because inode numbers are only unique within one filesystem, and it normally cannot point at a directory.

A **symbolic link** (or soft link) sidesteps both limits. It is a tiny file of its own whose contents are just a path, a signpost reading "look over there". It can span filesystems and point at directories, which is exactly why the usr merge wires [[bin]] and [[lib]] to their counterparts under [[usr]] with symlinks. The cost is fragility: delete the target and the symlink still exists but now dangles, pointing at nothing.

You create both with `ln`, adding `-s` for the symbolic kind. The first character of `ls -l` tells them apart at a glance: a plain `-` could be either a regular file or a hard link, while `l` marks a symlink.
