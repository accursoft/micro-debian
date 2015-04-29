Removed from the [official image](https://registry.hub.docker.com/_/debian/):

 - systemd
 - tzdata
 - bash (change `#!/bin/bash` to `#!/bin/sh` for dash)
 - iproute
 - passwd
 - various low-level system tools and libraries
 - doc (copyright files archived in `/usr/share/copyrights.tar.gz`)
 - man
 - info
 - locale (`apt-get install --reinstall libc-bin` to recover `C.UTF-8`)

`no-perl` removes perl-base and replaces debconf with cdebconf. Beware that many packages have an undeclared dependency on perl-base.
Sometimes this is only needed at install time, e.g. when installing ca-certificates due to [openssl issue #2324](http://rt.openssl.org/Ticket/Display.html?id=2324).

[test](test) will build both images and run a simple test. [equivs](https://packages.debian.org/equivs) is required to build `no-perl`.