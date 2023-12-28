---
tags:
  - projects
  - kasm
  - workspace
categories:
  - kasm
  - linux
---

# AppImage Kasm Workspace

[AppImage](https://appimage.org) is a format for distributing portable software on Linux without needing superuser permissions to install the application. It aims to enable application developers to deploy binary software without being restricted to specific Linux distributions, a concept often referred to as upstream packaging. In this manner, a single developed software can effortlessly run on any Linux distribution, such as Ubuntu, RHEL, or Arch.

Released first in 2004 under the name klik, it was continuously developed, then renamed in 2011 to PortableLinuxApps and later in 2013 to `AppImage`.

## Design

`AppImage` aims to be an application deployment system for Linux with the following objectives: **simplicity**, **binary compatibility**, **portability**, **distro agnosticism**, **no installation**, **no root permission**, and keeping the underlying operating system untouched.

`AppImage` does not install the application in the traditional Linux sense. Instead of putting the application's various files in the distribution's appropriate places in the file system, the `AppImage` file is a single file system image itself. When it runs, the file is mounted with `FUSE`.

Each file is self-contained: it includes all libraries the application depends on that are not already part of the targeted base-system. A version 1.0 `AppImage` is an ISO 9660 Rock Ridge file (which can be optionally `zisofs` compressed) containing a minimal AppDir and a tiny runtime. Version 2 may use other file system image formats like SquashFS.

`AppImage` files are simpler than installing an application. No extraction tools are needed, nor is it necessary to modify the operating system or user environment. Regular users on the common Linux distributions can download it, make it executable, and run it.

## AppImage Kasm Workspace

The `AppImage` Kasm workspace is designed to facilitate and ease the integration of AppImages into an Ubuntu 22.04 desktop environment. The workspace image includes [AppImageLauncher](https://github.com/TheAssassin/AppImageLauncher), a helper application for Linux distributions serving as a kind of "entry point" for running and integrating AppImages.

### Kasm volume mapping

The `AppImage` Kasm workspace should be deployed with a volume mapping in `/share` on the workspace. This maps `/share` in the Kasm workspace to a folder on the host. An administrator can place AppImages in the mapped `/share/AppImages` on the host. For example, with the following volume mapping configured in the `AppImage` workspace:

```json
{
  "/u/kasm_user_share": {
   "bind":"/share",
   "mode":"rw",
   "uid": 1000,
   "gid": 1000,
   "required": true,
   "skip_check": false
  }
}
```

AppImages on the host in `/u/kasm_user_share/AppImages` would be exposed in `/share/AppImages` in the workspace. If this mapping is used then the `appimage-launcher` utility will automatically discover and integrate AppImages located there.

## Kasm workspace persistent profile

The `AppImage` Kasm workspace should be deployed with a persistent profile. This preserves the home directory of the `kasm-user` user. For example, use the following persistent profile configured in the `AppImage` workspace:

```json
/u/kasm_profiles/{image_id}/{user_id}
```

Where `/u/kasm_profiles/` has been created on the Kasm server host.

Using a persistent profile in a Kasm workspace preserves any changes the the Kasm user's home directory across sessions allowing for personalized customization and configuration.

## Help documents

Record Technologies Kasm workspaces include a help facility that integrates the `ranger` file manager, the `glow` markdown previewer, and the `Obsidian` notes application. Help documents are provided in an Obsidian vault and can be browsed either directly with Obsidian or via the `ranger` file manager. Selecting a help document in `ranger` and pressing `<Enter>` will open Obsidian with the selected document.

## For users

### ![](https://github.com/encharm/Font-Awesome-SVG-PNG/raw/master/black/png/48/question-circle.png) What is an AppImage?

An AppImage is a downloadable file for Linux that contains an application and everything the application needs to run (e.g., libraries, icons, fonts, translations, etc.) that cannot be reasonably expected to be part of each target system.

### ![](https://github.com/encharm/Font-Awesome-SVG-PNG/raw/master/black/png/48/question-circle.png) How do I run an AppImage?

[Make it executable](http://discourse.appimage.org/t/how-to-make-an-appimage-executable/80) and double-click it.

### ![](https://github.com/encharm/Font-Awesome-SVG-PNG/raw/master/black/png/48/question-circle.png) How can I integrate AppImages with the system?

Using the optional `appimaged` daemon, you can easily integrate AppImages with the system. The daemon puts AppImages into the menus, registers MIME types, icons, all on the fly. You can download it from this repository. But it is entirely optional.

### ![](https://github.com/encharm/Font-Awesome-SVG-PNG/raw/master/black/png/48/question-circle.png) Where can I download AppImages?
See the "repository" of [upstream-generated AppImages](https://appimage.github.io/apps/).

### ![](https://github.com/encharm/Font-Awesome-SVG-PNG/raw/master/black/png/48/question-circle.png) Where do I store my AppImages?
If you don't want to leave them in `$HOME/Downloads`, then `$HOME/.local/bin` and `$HOME/bin` are good choices:
* On CentOS/RHEL and Fedora: When you login, the script `$HOME/.bash_profile` is executed and this script adds `$HOME/.local/bin:$HOME/bin` to your path.
* On Ubuntu: When you login, the script `$HOME/.profile` is executed and this script adds `PATH="$HOME/bin:$HOME/.local/bin"` to your path.

Besides, every other location works, e.g., a USB thumbdrive, a network location, or a CD-ROM, but then the AppImages won't be on your path, which means that you cannot simply type their name into a terminal but have to use the full path.

### ![](https://github.com/encharm/Font-Awesome-SVG-PNG/raw/master/black/png/48/question-circle.png) Where can I request AppImages?
If there is no AppImage of your favorite application available, please request it from the author(s) of the application, e.g., as a feature request in the issue tracker of the application. For example, if you would like to see an AppImage of Mozilla Firefox, then please leave a comment at https://bugzilla.mozilla.org/show_bug.cgi?id=1249971. The more people request an AppImage from the upstream authors, the more likely is that an AppImage will be provided.

### ![](https://github.com/encharm/Font-Awesome-SVG-PNG/raw/master/black/png/48/question-circle.png) Where do I get support?

Please visit http://discourse.appimage.org/. You can log in using your existing Google or GitHub account, no sign-up needed.

## For application developers

### ![](https://github.com/encharm/Font-Awesome-SVG-PNG/raw/master/black/png/48/question-circle.png) Why should I bundle my application as an AppImage?

By bundling your application as an AppImage, you can provide an official download for Linux like you would do for Windows and macOS where you as the application author can control the end-to-end user experience with no intermediaries between you as the author and your end user. With just one AppImage you can reach users of most Linux distributions. You can provide new download links as often as you like, e.g., for each continuous build.

Also, doing an AppImage has these advantages:
- Just one format for all major distributions
- Works out of the box, no installation of runtimes needed
- No root needed
- One app = one file = super simple for users
- Optional(!) desktop integration with `appimaged`
- Binary delta updates, e.g., for continuous builds (only download the binary diff) using AppImageUpdate
- Can GPG2-sign your AppImages (inside the file)

### ![](https://github.com/encharm/Font-Awesome-SVG-PNG/raw/master/black/png/48/question-circle.png) How do I bundle my application as an AppImage?

There are different ways to generate an AppImage of your application:

1. Convert existing binary packages, or
2. Bundle your Travis CI builds as AppImages, or
3. Run linuxdeployqt on your Qt application, or
4. Use electron-builder, or
5. Write your own

See https://github.com/probonopd/AppImageKit/wiki/Creating-AppImages for more information and examples.
