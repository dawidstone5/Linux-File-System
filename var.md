---
aliases:
  - /var
---

# var

`/var` is for variable data: the files a running system writes to and grows over time, as opposed to the fixed program code in [[usr]]. If something on disk changes while the machine simply runs, it probably belongs here.

The busy corners are worth knowing:

- `/var/log`: system and application logs, the first place to look when something breaks. `journalctl` and files like `/var/log/syslog` read from here.
- `/var/spool`: queued work waiting to be processed, such as print jobs and outgoing mail.
- `/var/cache`: data a program can regenerate, kept around to save time, like a package manager's downloaded archives.
- `/var/lib`: persistent state owned by services, for instance a database's actual files.
- `/var/tmp`: temporary files that, unlike those in [[tmp]], are meant to survive a reboot.

Because logs and spools can swell without warning, `/var` is often given its own partition so a runaway log file cannot fill up [[root|/]] and wedge the whole system. Its configuration, naturally, is set from [[etc]].
