Removed from the [official image](https://registry.hub.docker.com/_/debian/):

 - systemd
 - tzdata
 - bash (change `#!/bin/bash` to `#!/bin/sh` for dash)
 - iproute
 - various low-level system tools and libraries
 - doc (copyright files archived in `/usr/share/copyrights.tar.gz`)
 - man
 - info
 - locale (`apt-get install --reinstall libc-bin` to recover C.UTF-8)
 
Utility scripts provided:
 
 - `/opt/post-apt` cleans apt caches, logs, and installed docs
 - `/opt/dev` installs bash and ncurses-base for an interactive shell