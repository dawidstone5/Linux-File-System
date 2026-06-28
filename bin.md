# bin

`/bin` holds essential command binaries, the everyday tools every user relies on: `ls`, `cp`, `mv`, `cat`, `bash`. "Essential" has a precise meaning under the Filesystem Hierarchy Standard. These are the commands that must work even when [[usr|/usr]] is not mounted, for example during a single-user rescue boot.

That guarantee is why `/bin` sits directly under [[root|/]] rather than inside `/usr`. The two have to be on the same partition so the system can repair itself before any other disk is attached.

On most current distributions the old separation has collapsed into the "usr merge": `/bin` is now a symbolic link to `/usr/bin`, and the two names point at the same files. The distinction lives on mainly in documentation and in your muscle memory. Commands reserved for the administrator go to [[sbin]] instead, and the libraries these binaries load come from [[lib]].
