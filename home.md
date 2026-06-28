---
aliases:
  - /home
---

# home

`/home` holds the personal directories of ordinary users. Create a user called `dawid` and you get `/home/dawid`, owned by that user, where their files, downloads, and dotfiles live. The superuser is the exception; root keeps its home at [[root|/root]] instead.

This is the part of the tree people actually touch day to day, so it is often carved onto its own partition or disk. Keeping `/home` separate means you can wipe and reinstall the system under [[root|/]] without losing a single user file.

A user's shell configuration lives here as hidden dotfiles such as `.bashrc` and `.profile`. They override or extend the system-wide defaults kept in [[etc]]. Permissions matter most here: each home is normally readable and writable only by its owner, so one user cannot read another's private files.
