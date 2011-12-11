Bootgroom
=========

Description
-----------
Keeping kernel packages up-to-date means that many kernel packages gets
installed over time.  The task to remove older kernel is tedious. Furthermore,
if the /boot partition is full, the package manager can be stuck.  This script
will safely remove all unused kernels packages.  It will not remove the current
kernel, or the latest kernel installed. It will not remove unpackaged kernels,
as long as they didn't overwrite packaged kernels. By default it will also
remove linux-headers packages.

Because an half-installed kernel will make uninstallation impossible, initrd
files from packages to be removed are emptied first, and then apt-get -f
install will be run.

Requirements
------------
* A Debian-based distribution
* python-debian

Usage 
-----

`bootgroom`
will list the packages to be removed.
`bootgroom -v`
will list the packages to be removed and show the command it will run.
`bootgroom -c`
will remove all unused and outdated kernel and kernel headers packages, with
confirmation.

Options
-------
  -h, --help          show this help message and exit
  -v, --verbose       Display execution on stdout False]
  -H, --keep-headers  Don't remove linux-headers-* packages
  -c, --clean         Clean /boot
  -y, --yes           Assume yes for apt-remove
  -Y, --oh-yes        Assume yes (add -y for apt-remove)
  -q, --quiet         No output
