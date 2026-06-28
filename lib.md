# lib

`/lib` holds the shared libraries that the essential binaries in [[bin]] and [[sbin]] depend on, plus the kernel modules under `/lib/modules`. A shared library is code many programs reuse instead of each carrying its own copy; the C library `libc.so` is the one almost every program links against.

The most critical resident is the dynamic linker, `ld-linux.so`. When you run a program, this is the piece that finds the libraries it names, maps them into memory, and wires up the calls before the program's own code begins. Delete or corrupt it and almost nothing on the system will start, which is why these libraries sit beside [[root|/]] rather than under [[usr]].

You may also see `/lib64` on 64-bit machines, separating 64-bit objects from any 32-bit ones in `/lib`. As with [[bin]], the usr merge on modern distributions makes `/lib` a symlink into `/usr/lib`. Libraries for non-essential, packaged software live there.
