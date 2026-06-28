---
aliases:
  - inode
  - inodes
---

# inodes

An inode is the data structure that actually *is* a file, as far as the filesystem is concerned. It stores the metadata: the owner and group, the [[permissions]] bits, the timestamps, the size, the link count, and the addresses of the data blocks on disk. One thing it pointedly does not hold is the file's name.

That last detail explains a lot. A name is just an entry in a directory that points at an inode number, which is why the same inode can wear several names at once. Run `ls -i` and the first column is the inode number; two entries sharing a number are the same file under different names, the basis of hard [[links]].

Inodes are allocated when the filesystem is created, and the pool is finite. A disk can report plenty of free space yet still refuse new files because it ran out of inodes, a classic surprise on volumes full of tiny files. `df -i` shows that side of the ledger. The repair tool [[filesystem-types|fsck]] spends much of its time reconciling inodes against the directory entries that point to them, and the virtual files under [[proc]] are inode-like handles that map to no disk blocks at all.
