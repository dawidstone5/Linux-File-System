# usr

`/usr` is the second major hierarchy in the tree, and despite the spelling it is not about users. The name stands for Unix System Resources. Think of it as the read-only bulk of the installed system: the programs, libraries, and data that come from packages rather than from you or the kernel.

It mirrors the layout near [[root|/]]:

- `/usr/bin`: the vast majority of user commands. On modern distributions [[bin|/bin]] is just a symlink pointing here.
- `/usr/sbin`: non-essential administration tools, the companion to [[sbin]].
- `/usr/lib`: libraries backing the programs in `/usr/bin`, paralleling [[lib]].
- `/usr/local`: software you compiled or installed by hand, kept apart so a package manager never overwrites it.
- `/usr/share`: architecture-independent data such as manual pages, icons, and locale files.

The split exists for a historical reason that still pays off. Everything needed to boot and repair the machine sits under `/`, so `/usr` can live on a slower or even network-mounted disk and be attached after the system comes up. Variable runtime data does not belong here; that goes to [[var]].
