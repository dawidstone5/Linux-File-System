# Linux-File-System
---
The Linux File System is part of the Linux Operating System, responsible for organizing and managing data on storage devices.
From the root [[root]] directory denoted by `/`  (the tip or apex of file tree in Linux), we discuss the files found in each of the directories there is and their role.

The Linux file system is a critical part of . Here's a breakdown of its key features and structure:

## 1. **Hierarchy and Structure**
   - **Root Directory (`/`)**: The Linux file system is structured as a single tree hierarchy starting from the root directory, denoted by `/`.
   - **Directories and Files**: Everything in Linux is treated as a file, including directories, devices, and even processes.
   - **Standard Directories**: Linux systems follow a standard directory structure defined by the Filesystem Hierarchy Standard (FHS). Key directories include:
     - [[bin]] `/bin`: Essential command binaries like `ls`, `cp`, `mv`.
     - [[boot]] `/boot`: Boot loader files, including the kernel.
     - [[dev]] `/dev`: Device files, representing hardware components.
     - [[etc]] `/etc`: System configuration files.
     - [[home]] `/home`: User home directories.
     - [[lib]] `/lib`: Essential shared libraries and kernel modules.
     - [[mnt and media]] `/mnt` and `/media`: Mount points for temporary and removable filesystems.
     - [[opt]] `/opt`: Optional software packages.
     - [[proc]] `/proc`: Virtual filesystem providing information about processes.
     - [[root]] `/root`: Home directory for the root user.
     - [[sbin]] `/sbin`: System binaries, mainly for root use.
     - [[tmp]] `/tmp`: Temporary files.
     - [[usr]] `/usr`: Secondary hierarchy with user applications.
     - [[var]] `/var`: Variable data like logs, databases.

## 2. **File Types**
   - **Regular Files (`-`)**: Ordinary files, such as text, executables, and scripts.
   - **Directories (`d`)**: Containers that hold other files and directories.
   - **Symbolic Links (`l`)**: Pointers to other files or directories.
   - **Device Files**: Represent hardware devices, split into:
     - **Block Devices (`b`)**: For devices that read/write in blocks (e.g., hard drives).
     - **Character Devices (`c`)**: For devices that handle data as a stream of characters (e.g., keyboards).
   - **Pipes and Sockets (`p` and `s`)**: Used for inter-process communication.

## 3. **Permissions**
   - **User (u), Group (g), and Others (o)**: Each file and directory has permissions associated with the owner (user), the group, and others.
   - **Permission Types**:
     - **Read (`r`)**: Ability to read the file or list directory contents.
     - **Write (`w`)**: Ability to modify the file or directory contents.
     - **Execute (`x`)**: Ability to execute the file or access the directory.

## 4. **File System Types**
   - **Ext4**: The most common default file system in Linux, known for robustness and performance.
   - **XFS**: High-performance file system suited for large files.
   - **Btrfs**: Modern file system with advanced features like snapshots and self-healing.
   - **FAT32, NTFS**: Often used for compatibility with Windows systems.

## 5. **Mounting and Unmounting**
   - **Mounting**: The process of making a file system accessible at a certain point in the directory tree. For example, `mount /dev/sda1 /mnt` would mount a partition to `/mnt`.
   - **Unmounting**: Detaching a file system from the directory tree, done with `umount /mnt`.

## 6. **Inodes**
   - **Inodes**: Data structures that store metadata about files, such as ownership, permissions, and location of the actual data blocks. Each file has an inode, identified by an inode number.

## 7. **Links**
   - **Hard Links**: Multiple directory entries for the same file, pointing to the same inode.
   - **Soft (Symbolic) Links**: Pointers to another file or directory.

## 8. **File Operations**
   - **Basic Commands**:
     - `ls`: List directory contents.
     - `cd`: Change directory.
     - `cp`, `mv`, `rm`: Copy, move, and remove files.
     - `mkdir`, `rmdir`: Create and remove directories.
     - `chmod`, `chown`, `chgrp`: Change file permissions and ownership.

## 9. **Special File Systems**
   - **Procfs (`/proc`)**: A pseudo-file system that provides a view into the kernel's view of processes and system information.
   - **Sysfs (`/sys`)**: Exposes kernel devices and their attributes.

## 10. **File System Maintenance**
   - **fsck**: File system check and repair tool.
   - **mkfs**: Create a file system on a partition or storage device.
   - **mount options**: Customize file system behavior (e.g., read-only, noexec).
