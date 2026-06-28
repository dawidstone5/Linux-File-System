---
aliases:
  - /srv
---

# srv

`/srv` is for data that this machine serves to the outside world. A web server's pages might live in `/srv/www`, an FTP area in `/srv/ftp`, a Git repository under `/srv/git`. The point of the directory is organisational: anyone landing on the box should be able to tell at a glance where its served content sits.

It draws a useful line against neighbours that look similar. Configuration for those same services belongs in [[etc]], their installed program code in [[usr]], and their internal working state in `/var/lib` under [[var]]. `/srv` is reserved for the actual payload the service hands out.

In practice many distributions leave `/srv` empty and administrators wire things up however they prefer, so the Filesystem Hierarchy Standard sets the intent without dictating the layout inside. Whether you use it at all is a site policy decision, not a system requirement.
