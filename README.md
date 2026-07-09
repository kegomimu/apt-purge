# apt-purge

A simple package which removes a package completely

## The problem
`apt purge` or `dpkg purge` does not completely remove created folders, files, users, groups and services of a package.

For example does `apt purge libvirt0` and `apt-get autoclean` remove the package `libvirt0` but not the created libvirt and kvm users as well as the libvirt-qemu group. Folders such as `/etc/libvirt` and `/lib/libvirt` also persist.

## The solution
`apt-purge` works by scanning services, files and folders, users and groups for any connection to the package to be removed. The package is fully removed, using `apt purge`, `apt-get autoclean` and own implementations.