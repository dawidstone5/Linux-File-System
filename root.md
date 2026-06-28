# root

The word "root" means two different things in Linux, and they sit at opposite ends of the tree.

## The root directory `/`

`/` is the apex of the whole hierarchy. Every other path hangs off it, which is why an absolute path always begins with a slash. There is no directory above `/`; it is its own parent. A single tree like this is also why Linux has no drive letters. A second disk does not become `D:`, it gets [[mnt and media|mounted]] somewhere inside the existing tree.

Most of what lives directly under `/` is itself a directory: [[bin]], [[boot]], [[dev]], [[etc]], [[home]], [[lib]], [[opt]], [[proc]], [[sbin]], [[tmp]], [[usr]], [[var]], and the root user's home below.

## The root user's home `/root`

`/root` is the home directory of the superuser, the account named `root` with UID 0. It is kept separate from the regular [[home]] tree on purpose. During early boot or a rescue session `/home` may sit on a disk that is not mounted yet, so the administrator's home has to live on the same filesystem as `/` to stay reachable.

The two meanings are easy to keep apart: `/` is where the filesystem starts, `/root` is where the most powerful user lives.
