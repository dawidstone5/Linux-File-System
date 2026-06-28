# opt

`/opt` is for optional, self-contained software, usually third-party applications that ship outside the distribution's package system. The idea is that a vendor drops everything for one product into a single directory, such as `/opt/google/chrome`, where the binary, its libraries, and its data all sit together.

This keeps such software from scattering pieces across [[bin]], [[lib]], and [[usr]] the way a native package does. Removing the application is then as simple as deleting its folder, with nothing left behind elsewhere.

It contrasts with `/usr/local` under [[usr]], which is the place for software you compiled yourself and which still follows the standard `bin`/`lib`/`share` split. Roughly: `/opt` for prepackaged vendor blobs that bring their own layout, `/usr/local` for things you build to fit the system's. Any settings or runtime files an `/opt` program needs still tend to land in [[etc]] and [[var]] respectively.
