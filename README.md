# apt-purge

A simple package which removes packages and their doings completely

## The problem
`apt purge` or `dpkg purge` does not completely remove created folders, files, users, groups and services of a package.

For example does `apt purge libvirt0` and `apt-get autoclean` remove the package `libvirt0` but not the created libvirt and kvm users as well as the libvirt-qemu group. Folders such as `/etc/libvirt` and `/lib/libvirt` also persist.

## The solution
`apt-purge` works by scanning services, files, folders, users and groups for any connection to the package to be removed.

## How does it work

1. The services are stopped if they are currently active
2. The services are disabled
3. `apt purge` and `apt-get autoclean`
4. Users, groups, folders and files are scanned for connections to the service to be removed
5. All findings will be deleted while not destroying the OS