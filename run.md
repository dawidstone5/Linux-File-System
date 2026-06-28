# run

`/run` holds volatile runtime data that programs produce while the system is up: process IDs, lock files, sockets, and similar bookkeeping that describes the current boot. It is normally a `tmpfs` living in RAM, so it starts empty at every boot and never persists.

It exists to fix an old muddle. This kind of data used to be scattered across `/var/run` and `/var/lock` inside [[var]], but those sit on disk and may not be mounted early in boot when the first daemons already need somewhere to write. `/run` is mounted very early and solves that cleanly. For compatibility `/var/run` is now usually a symlink pointing back here.

A typical resident is `/run/sshd.pid`, the file recording the SSH daemon's process ID so scripts can find and signal it. Because everything here evaporates on reboot, nothing in `/run` is ever meant to be a permanent record; logs and lasting state belong in [[var]] instead, and the persistent kernel device view is over in [[sys]].
