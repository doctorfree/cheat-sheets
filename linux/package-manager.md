# Package Manager

A package manager or package-management system is a collection of software tools that automates the process of installing, upgrading, configuring, and removing computer programs for a computer in a consistent manner.

A package manager deals with packages, distributions of software and data in archive files. Packages contain metadata, such as the software's name, description of its purpose, version number, vendor, checksum (preferably a cryptographic hash function), and a list of dependencies necessary for the software to run properly. Upon installation, metadata is stored in a local package database. Package managers typically maintain a database of software dependencies and version information to prevent software mismatches and missing prerequisites. They work closely with software repositories, binary repository managers, and app stores.

Package managers are designed to eliminate the need for manual installs and updates. This can be particularly useful for large enterprises whose operating systems typically consist of hundreds or even tens of thousands of distinct software packages.

| **Action** | **zypper** | **pacman** | **apt** | **dnf (yum)** | **swupd** | **portage** | **Nix** | **Homebrew** | **WinGet** | **xbps** |
| ---------- | ---------- | ---------- | ------- | ------------- | --------- | ----------- | ------- | ------------ | ---------- | -------- |
| Install package | `zypper in ${PKG}` | `pacman -S ${PKG}` | `apt install ${PKG}` | `dnf install ${PKG}` | `swupd bundle-add ${PKG}` | `emerge ${PKG}` | `nix-env -i ${PKG}` | `brew install ${PKG}` | `winget install %PKG%` | `xbps-install ${PKG}` |
| Remove package | `zypper rm -RU ${PKG}` | `pacman -R ${PKG}` | `apt remove ${PKG}` | `dnf remove --nodeps ${PKG}` | `swupd bundle-remove ${PKG}` | `emerge -C ${PKG}` or `emerge --unmerge ${PKG}` | `nix-env -e ${PKG}` | `brew rm ${PKG}` (rm is shorthand for remove or uninstall) | `winget uninstall %PKG%` | `xbps-remove ${PKG}` |
| Remove package (and orphans) | `zypper rm -u --force-resolution ${PKG}` | `pacman -Rs ${PKG}` | `apt autoremove ${PKG}` | `dnf remove ${PKG}` | `swupd bundle-remove ${PKG} && swupd bundle-remove --orphans` | `emerge -c ${PKG}` or `emerge --depclean ${PKG}` | `nix-env -e ${PKG} && nix-env -u` | `brew rm ${PKG} && brew autoremove` | `winget uninstall %PKG%` | `xbps-remove -R ${PKG}` |
| Update software database | `zypper ref` | `pacman -Sy` | `apt update` | `dnf check-update` | `swupd update --download` or `swupd update --update-search-file-index` | `emerge --sync` | `nix-channel --upgrade` | `brew update` | `winget list > NUL` | `xbps-install -S` |
| Show updatable packages | `zypper lu` | `pacman -Qu` | `apt list --upgradable` | `dnf check-update` | `swupd update -s` or `swupd check-update` | `emerge -avtuDN --with-bdeps=y @world` or `emerge -u --pretend @world` (-D is shorthand for --deep and -u is shorthand for --update.) | `nix-channel --upgrade && nix-env -u && nix-collect-garbage` | `brew outdated` | `winget upgrade` | `./xbps-src update-check ${PKG}` (requires void-packages repository) |
| Delete orphans and config | `zypper rm -u` | `pacman -Rsn $(pacman -Qdtq)` | `apt autoremove` | `dnf erase ${PKG}` | `swupd bundle-remove --orphans && swupd clean --all` | `emerge --depclean` | `nix-collect-garbage -d` | `brew unlink ${PKG} && brew clean` | | | `xbps-remove -of` |
| Show orphans | `zypper pa --orphaned --unneeded` | `pacman -Qdt` | | `package-cleanup -q --leaves --exclude-bin` (-q is shorthand for --quiet.) | `swupd bundle-list --orphans` | `emerge -caD` or `emerge --depclean --pretend` | | | | `xbps-remove -o` |
| Update all | `zypper up` | `pacman -Syu` | `apt upgrade` | `dnf update` | `swupd update` | `emerge -u -D --with-bdeps=y @world` | `nix-env -u && nix-collect-garbage` | `brew upgrade` | `winget upgrade --all` | `xbps-install -Su` |

## See also

- [Arch Linux Pacman/Rosetta wiki](https://wiki.archlinux.org/title/Pacman/Rosetta)
- [Awesome Package Manager](https://github.com/jubalh/awesome-package-maintainer#readme)
- [Flatpak](flatpak.md)
- [Pacman](pacman.md)
