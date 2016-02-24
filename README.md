Ubuntu Grsecurity
=================

Overview
--------

[Grsecurity](https://grsecurity.net/) is a patch for the
[Linux kernel](https://www.kernel.org/) that aggressively mitigates security
exploits.

This project builds a kernel package for [Ubuntu](http://www.ubuntu.com/).
Because we do not have the ability to modify the Ubuntu userland to apply
compatibility patches, this project uses a conservative grsecurity
configuration that is unlikely to break userland software.

The dpkg pre/post installation/removal scripts are taken from Ubuntu 16.04,
and should be kept in sync with upstream Ubuntu releases.

Build Instructions
------------------

```
# Import Brad Spengler's GPG key
gpg --recv 2525FE49

# Import the Linux stable GPG key
gpg --recv 6092693E

# Build linux-grsecurity_<version>.deb
fakeroot make
```

Firmware
--------

This package does NOT include the firmware that many devices will need to
function. However, because this kernel will typically be more recent than
any Ubuntu release, it may refer to firmware not included in your
[``linux-firmware``](http://packages.ubuntu.com/source/wily/linux-firmware)
package.

It is best to install the newest available firmware packages from
<http://archive.ubuntu.com/ubuntu/pool/main/l/linux-firmware/?C=M;O=D>.
