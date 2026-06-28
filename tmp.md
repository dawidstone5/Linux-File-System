# tmp

`/tmp` is scratch space. Any program can write here, and any user can create files, which is what makes it useful for short-lived data like a download in progress or an editor's swap file.

Two rules define it. First, do not expect anything to survive: many systems clear `/tmp` on reboot, and some mount it as a `tmpfs` that lives entirely in RAM and vanishes when power drops. Second, the directory carries the sticky bit (`drwxrwxrwt`, note the trailing `t`). Everyone can write into `/tmp`, but the sticky bit stops one user from deleting or renaming another user's files, which closes an obvious abuse.

For data that should persist across reboots but is still expendable, the right place is `/var/tmp` under [[var]], not here. Long-lived files belong in [[home]] or, for packaged software, under [[usr]].
