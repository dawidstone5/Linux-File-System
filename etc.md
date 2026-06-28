# etc

`/etc` is the system's configuration drawer. It holds host-specific settings as plain text files, which is one of the quietly powerful ideas in Unix: you can read, diff, edit, and version-control your entire machine's behaviour with nothing more than a text editor.

A few you will meet early:

- `/etc/passwd` and `/etc/shadow`: the user accounts and their hashed passwords.
- `/etc/fstab`: the table that says which filesystems to mount where at boot, the static counterpart to the live mounts under [[mnt and media]].
- `/etc/hostname` and `/etc/hosts`: the machine's name and its local name lookups.
- `/etc/ssh/sshd_config`: how the SSH server behaves.

The rule that keeps `/etc` honest is that it contains no binaries. Programs live in [[bin]], [[sbin]], and [[usr]]; their settings live here. These files set the defaults for the whole system, which individual users can then override with the dotfiles in their own [[home]] directory.
