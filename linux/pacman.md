# Pacman Arch Linux Package Manager

All Arch Linux packages are managed using the Pacman package manager. Pacman handles package installation, upgrades, downgrades, removal and features automatic dependency resolution. The packages for Arch Linux are obtained from the Arch Linux package tree and are compiled for the x86-64 architecture. It uses binary packages in the `tar.zst` (for zstd compression), with `.pkg` placed before this to indicate that it is a Pacman package (giving `.pkg.tar.zst`).

For example, packages can be installed via `pacman -S package name`, while `pacman -Syu` can also be used to perform a full system upgrade.

Pacman is also used for installing packages under MSYS2 (a fork of Cygwin) on Windows.

| **Command** | **Description** |
| ----------- | --------------- |
| `sudo pacman -Syy` | Update package list |
| `sudo pacman -Syu` | Update and upgrade all |
| `sudo pacman -S pkgname` | Install specific package |
| `sudo pacman -Ss keyword` | Find available packages |
| `sudo pacman -Qs keyword` | Find available local packages |
| `sudo pacman -Ql pkgname` | List all files from a package |
| `sudo pacman -Rsc pkgname` | Uninstall a package |
| `sudo pacman -Qii pkgname` | List information on package |
| `sudo pacman -Qdt` | List no longer required dependencies |

## Table of Contents

- [Repositories](#repositories)
  - [Arch User Repository](#arch-user-repository)
- [Arch Build System](#arch-build-system)
- [Pacman cheat sheet](#pacman-cheat-sheet)

## Repositories

The following official binary repositories exist:

- `core`, which contains all the packages needed to set up a base system. Packages in this repository include kernel packages and shell languages.
- `extra`, which holds packages not required for the base system, including desktop environments and programs.
- `community`, which contains packages built and voted on by the community; includes packages that have sufficient votes and have been adopted by a "trusted user".
- `multilib`, a centralized repository for x86-64 users to more readily support 32-bit applications in a 64-bit environment. Packages in this repository include Steam and Wine.

### Arch User Repository

In addition to the official repositories, there are a number of unofficial user repositories.

The most well-known unofficial repository is the
[Arch User Repository](https://aur.archlinux.org/), or AUR, hosted on the Arch Linux site.

The AUR does not host binary packages but instead a collection of build scripts known as PKGBUILDs. PKGBUILD scripts are executed by the `makepkg` command, which downloads the necessary files from the software's repository and builds them using the Arch Build System.

Installing packages from the AUR is a relatively simple process. Essentially:

- Acquire the build files, including the PKGBUILD and possibly other required files, like systemd units and patches (often not the actual code).
- Verify that the PKGBUILD and accompanying files are not malicious or untrustworthy.
- Run `makepkg` in the directory where the files are saved. This will download the code, compile it, and package it.
- Run `pacman -U package_file` to install the package onto your system.

These PKGBUILD scripts simplify building from source by explicitly listing and checking for dependencies and configuring the install to match the Arch architecture. Arch User Repository helper programs can further streamline the downloading of PKGBUILD scripts and associated building process.

Users can create packages compatible with Pacman using the Arch Build System and custom PKGBUILD scripts. This functionality has helped support the Arch User Repository, which consists of user contributed packages to supplement the official repositories.

## Arch Build System (ABS)

The Arch Build System (ABS) is a ports-like source packaging system that compiles source tarballs into binary packages, which are installed via Pacman. The Arch Build System provides a directory tree of shell scripts, called PKGBUILDs, that enable any and all official Arch packages to be customized and compiled. Rebuilding the entire system using modified compiler flags is also supported by the Arch Build System. The Arch Build System `makepkg` tool can be used to create custom `pkg.tar.zst` packages from third-party sources. The resulting packages are also installable and trackable via `pacman`.

## Pacman cheat sheet

### Update package list

```shell
sudo pacman -Syy
```

### Update and upgrade all

```shell
sudo pacman -Syu
```

### Install specific package

```shell
sudo pacman -S pkgname
```

### Find available packages

```shell
sudo pacman -Ss keyword
```

### Find available local packages

```shell
sudo pacman -Qs keyword
```

### List all files from package

```shell
pacman -Ql pkgname
```

### Pacman log file

`/var/log/pacman.log`

### Screen recording

`gtk-recordmydesktop`

### Mount iso file

```shell
fuseiso -p  testimage.iso testimagemountpoint
```

### To unmount

```shell
fusermount -u <mountpoint>
```
  
### To remove a package and its dependencies which are not required by any other installed package

```shell
sudo pacman -Rs package_name
```

### List all packages no longer required as dependencies

```shell
sudo pacman -Qdt
```

### Get IP address

```shell
ip addr
```

### Update and upgrade yaourt packages

```shell
yaourt -Syua
```

### Get distro version

```shell
lsb_release -a
```
