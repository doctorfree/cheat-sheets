# Release Notes

## Table of contents

1. [Overview](#overview)
1. [Installation](#installation)
1. [Configuration](#configuration)
1. [Removal](#removal)
1. [Support](#support)
1. [Changelog](#changelog)

## Overview

The Cheat Sheets Plus repository is an [Obsidian](https://obsidian.md) vault containing cheat sheets, project information, documentation, code snippets, and other useful information in markdown format. The main feature of this knowledge base repository is that the markdown files have been manicured to contain internal backlinks and tags thus exposing their inter-relationships. It's a knowledge base with metadata providing insight.

It can be viewed using any markdown viewer (e.g. almost any browser) but if Obsidian is used then many additional features will be available including queries using the [Dataview](https://blacksmithgu.github.io/obsidian-dataview/) plugin for [Obsidian](https://obsidian.md/).

This knowledge base has been developed through the efforts of several individuals. It is licensed under the [MIT open source license](LICENSE) and can be shared freely as long as the individual copyrights are retained. Please feel free to contribute with additional cheat sheets and documentation, corrections, suggestions, enhancements, or simply buy us a cup of coffee.

These are the release notes for Version 1.0.1 Release 1 of the Cheat Sheets Plus vault.

## Installation

The Cheat Sheets Plus vault can be installed on Windows, Mac, or Linux. The following installation instructions are for Mac and Linux. Windows users can follow similar steps.

**For the optimal experience, open this vault in Obsidian!**

1. [Download the vault](https://github.com/doctorfree/cheat-sheets-plus/releases/latest)
3. Open the vault in Obsidian via "Open another vault -> Open folder as vault"
4. Trust us. :) 
5. When Obsidian opens the settings, hit the switch on "Dataview" to enable the plugin
6. Done! The Cheat Sheets Plus vault is now available to you in its purest and most useful form!

### Download the release archive

[Download the latest release](https://github.com/doctorfree/cheat-sheets-plus/releases/latest).

Those familiar with `wget` can download this release from the command line with:

```shell
wget --quiet -O ~/Downloads/cheat-sheets-plus-v1.0.1r1.tar.gz \
  https://github.com/doctorfree/cheat-sheets-plus/archive/refs/tags/v1.0.1r1.tar.gz
```

### Extract the release archive

Currently release archives are available in either ZIP or compressed tar archive format.

To extract the ZIP archive:

```shell
cd /path/to/your/vaults # e.g. `cd ~/Documents/Obsidian`
unzip /path/to/cheat-sheets-plus-1.0.1r1.zip
```

To extract the compressed tar archive:

```shell
cd /path/to/your/vaults # e.g. `cd ~/Documents`
tar xf /path/to/cheat-sheets-plus-1.0.1r1.tar.gz
```

Once extracted, the Cheat Sheets Plus vault is now available in `/path/to/your/vaults/cheat-sheets-plus-1.0.1r1/`.

The downloaded archive can be deleted:

```shell
rm -f /path/to/cheat-sheets-plus-1.0.1r1.zip
```

or

```shell
rm -f /path/to/cheat-sheets-plus-1.0.1r1.tar.gz
```

## Configuration

The Cheat Sheets Plus vault is pre-configured for use with [Obsidian](https://obsidian.md). Install Obsidian for your platform by clicking the appropriate installation link at the Obsidian website. Obsidian is available for Windows, Mac, and Linux as well as mobile devices.

Add a new vault in Obsidian with `Open folder as vault` and navigate to the `cheat-sheets-plus-1.0.1r1` extracted folder. When prompted, `Trust` and enable the `Dataview` plugin if it is not already enabled.

The Cheat Sheets Plus vault includes the `Doctorfree` Obsidian theme. Enable this Obsidian theme in Obsidian by visiting `Settings -> Appearance` and selecting `Doctorfree` from the dropdown in the `Themes` section.

Obsidian is required for some features but is not necessary to view the Cheat Sheets Plus vault. Any markdown viewer/editor can be used. If the Cheat Sheets Plus vault is extracted into a website folder, it can be viewed using most browsers.

## Removal

To remove the Cheat Sheets Plus vault simply remove the extracted folder and its contents:

```shell
cd /path/to/your/vaults # e.g. `cd ~/Documents/Obsidian`
rm -rf cheat-sheets-plus-1.0.1r1
```

## Support

Support the development and improvement of the Cheat Sheets Plus vault by [sponsoring the Projects of Doctorfree](https://github.com/sponsors/doctorfree).

<a href="https://www.buymeacoffee.com/doctorfree"><img src="https://img.buymeacoffee.com/button-api/?text=Buy me a coffee&emoji=&slug=doctorfree&button_colour=5F7FFF&font_colour=ffffff&font_family=Lato&outline_colour=000000&coffee_colour=FFDD00"></a>

## Changelog

View the full changelog for this release at https://github.com/doctorfree/cheat-sheets-plus/blob/v1.0.1r1/CHANGELOG.md
