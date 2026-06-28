# proc

`/proc` is a window into the running kernel, not a place on any disk. It is a virtual filesystem: the files you see are generated on demand by the kernel when you read them, so they cost nothing until touched and always show the current state.

Its original job is in the name. For every running process there is a numbered directory, `/proc/1234`, exposing that process's command line, open files, memory map, and environment. Tools like `ps` and `top` are mostly just polite readers of these files.

Over time it also became the dashboard for the system as a whole. `cat /proc/cpuinfo` lists your processors, `/proc/meminfo` reports memory use, and writable knobs under `/proc/sys` let you tune the kernel live. That tuning role is increasingly shared with `/sys`. None of this is the same as the hardware handles in [[dev]]: `/proc` reports on software and kernel state, while `/dev` lets you talk to devices. Persistent metadata about files on disk lives instead in their inodes, not here.
