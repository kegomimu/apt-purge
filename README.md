# apt-purge

A simple package which removes a package completely

## The problem
`apt purge` or `dpkg purge` does not completely remove created folders, files, users, groups and services of a package.

## `apt-purge`
`apt-purge` works by scanning services, files and folders, users and groups for any connection to the package to be removed. The package is fully removed, using `apt purge`, `apt-get autoclean` and own implementations.