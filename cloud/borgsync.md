The `borgsync` command is a wrapper to simplify backups with `borgbackup` and provide command line management of an [rsync.net](https://rsync.net) and/or [BorgBase](https://www.borgbase.com) off-site storage account.

## Table of Contents

- [Overview](#overview)
- [Requirements](#requirements)
- [Installation](#installation)
- [Configuration](#configuration)
  - [Custom configurations](#custom-configurations)
  - [Configuration specification](#configuration-specification)
- [Usage](#usage)
- [Automated scheduled backups](#automated-scheduled-backups)
  - [Automated backups using cron](#automated-backups-using-cron)
  - [Automated backups using systemd](#automated-backups-using-systemd)
- [Examples](#examples)
- [Borg server preparation](#borg-server-preparation)
- [See also](#see-also)

## Overview

The `borgsync` command can be used to manage cloud storage on [rsync.net](https://www.rsync.net), [BorgBase](https://www.borgbase.com), or any remote server with `ssh` access.

`borgsync` supports remote backups using the [borg](https://www.borgbackup.org) deduplicating archiver with compression and encryption.

Several excellent wrappers and front-ends for `borg` exist. The `borgsync` command attempts to be simple, easy to setup and use, while still being fully enough featured to satisfy the off-site storage and backup needs of most users.

Setup, configuration, and use of `borgsync` is easy:

* [Install](#installation): `git clone ...` and `./install`
* [Configure](#configuration): set `REMOTE_USER` and `REMOTE_HOST` in `/etc/borgsync/base`
* Initialize a `borg` backup repository with `borgsync -b init`
* Create the default `borg` backup with `borgsync`

In addition to managing `borg` backups, the `borgsync` command can be used to upload/manage files and folders on the remote storage service through `ssh`.

For a more complex and thorough approach, see [Borgmatic](https://torsion.org/borgmatic).

In order to use `borgsync` an `rsync.net` or `BorgBase` account is not required but defaults are configured for use with either `rsync.net` or `BorgBase`.

Pricing for these two popular and well maintained off-site storage services ranges from $5-$10 per terabyte per month. BorgBase is cheaper, rsync.net offers some additional features, both are excellent and affordable. BorgBase offers a free trial plan with 10GB storage and 2 repositories along with automated extension of your plan based on usage.

The author of `borgsync` is not affiliated with any storage service and does not receive any compensation for this effort.

## Requirements

The `borgsync` command can be installed on `Linux` or `macOS`. It is a command line utility requiring a terminal or console and the `Bash` shell.

## Installation

To install `borgsync` clone this repository and run the `install` script:

```bash
git clone https://github.com/doctorfree/borgsync
cd borgsync
./install
```

The `install` script can be run either as the `root` user or as a user with `sudo` privilege. The `install` script will check if the `borg` command is in your `PATH` and, if not, it will download and install the latest release of `borg`.

After ensuring that `borg` is installed the `install` script copies the `borgsync` command into `/usr/local/bin/`.

In addition, the Borg Backup GUI [Vorta](https://vorta.borgbase.com) is installed.

To install the `borgsync` command and configuration files in the user's home rather than system-wide, invoke the `install` script with the `user` argument:

```bash
./install user
```

If `borgsync` is installed in the user home, add `$HOME/.local/bin` to your `PATH`.

***At this point your system is ready but borgsync is not yet configured***

Follow the steps in the [Configuration section](#configuration) to complete the installation and configuration of `borgsync`.

## Configuration

By default `borgsync` expects the base system-wide configuration to be located at `/etc/borgsync/base`. Individual users can override these defaults in `~/.config/borgsync/base`. An example configuration file is included in [config/base](config/base).

The `install` script copies the example configuration to `/etc/borgsync/base` but the remote user and host must be set manually:

```bash
vi /etc/borgsync/base    # customize with your storage service user/host/etc
```
### Custom configurations

Several custom configurations are installed in `/etc/borgsync/`:

* [/etc/borgsync/base](config/base): the default configuration, used as the base for all others
* [/etc/borgsync/full](config/full): perform a full system backup (`borgsync -b create -t full`)
* [/etc/borgsync/home](config/home): backup /home (`borgsync -b create -t home`)
* [/etc/borgsync/logs](config/logs): backup /var/log (`borgsync -b create -t logs`)
* [/etc/borgsync/photos](config/photos): backup a photo library (`borgsync -b create -t photos`)
* [/etc/borgsync/test](config/test): example backup using BorgBase (`borgsync -b create -t test`)

Additional custom configurations can be created by adding files to `/etc/borgsync` or `~/.config/borgsync`. Use the `-t <name>` argument to specify the `/etc/borgsync/<name>` configuration. Custom configurations all use `/etc/borgsync/base` as the base configuration. Only configuration variables that differ from the base need to be specified in a custom configuration.

## Configuration specification

Details of the `borgsync` configuration specification can be found in [/etc/borgsync/README.md](config/README.md).

## Usage

Get started with `borgsync` by editing `/etc/borgsync/base` and setting the `REMOTE_USER` and `REMOTE_HOST` variables to your storage service user and host. For example, an `rsync.net` account for user `fm1872` would have the following settings in `/etc/borgsync/base`:

```bash
REMOTE_USER="fm1872"
REMOTE_HOST="fm1872.rsync.net"
```

The defaults in `/etc/borgsync/base` should suffice for most users but backup paths, exclusions, options, and more can be customized. Once these are configured:

* Initialize a `borg` backup repository with the command `borgsync -b init`
* Create the default `borg` backup with the command `borgsync`

The `borgsync` usage message can be displayed with `borgsync -u`:

```
Usage: borgsync [-b init|check|create|delete|extract|info|list|mount|umount]
                [-a archive] [-B] [-C config] [-c cmd] [-d dir] [-lLn] [-m mnt]
                [-U user] [-H host] [-qQruvV] [-t base|full|home|logs] folder
Where:
	-a 'archive' specifies the borg repository archive name to use
	-B indicates download and update the latest borgsync and borg binary
	-b 'init' initializes a borg backup repository
	-b 'check' verifies the consistency of the borg backup repository
	-b 'create' creates a borg backup on remote storage
	   combine with '-t base|full|home|logs' (default: base)
	-b 'delete' deletes the borg backup repository on remote storage
	-b 'extract' lists what would be extracted and provides a command to extract
	   use the 'folder' argument to provide a pattern to match for extraction
	-b 'info' displays detailed information about the borg backup repository
	-b 'list' lists all archives in the borg backup repository
	-b 'mount' mounts the borg backup repository on /mnt/borg
	-b 'umount' unmounts the borg backup repository from /mnt/borg
	-C '/path/to/config' specifies the base config file (default: /etc/borgsync/base)
	-c 'cmd' runs command 'cmd' on the remote storage host
	-d 'dir' specifies a borg backup directory (default: base)
	-l indicates list the contents of the backup folder
	-L indicates recursively list the contents of the backup folder
	-m 'mnt' specifies the mount point for the borg repo (default: /mnt/borg)
	-n indicates perform a dry run, don't make any changes
	-q indicates see how much space your account uses with the quota/df commands
	-Q indicates see how much space your account uses with the quota/df/du commands
	-r indicates remove remote backup
	-t 'conf' specifies an alternate borgsync config file to use
	   '-t fubar' will use the borgsync config file /etc/borgsync/fubar
	-v indicates verbose mode
	-V displays the borgsync version and exits
	-U 'user' sets the remote storage user to 'user'
	-H 'host' sets the remote storage host to 'host'
	-u displays this usage message and exits

The 'folder' argument indicates the remote storage folder to sync/list/remove
Without arguments borgsync performs the default borg backup
```

## Automated scheduled backups

Automated periodic backups can be scheduled with `systemd` or `cron`

### Automated backups using cron

To automate daily remote backups with the `borgsync` command, verify that the `root` user can access the `rsync.net` account using `ssh` without being prompted. Copy the `$HOME/.config/borg/` folder to `/root/.config/borg/` and set the `BORG_PASSPHRASE` environment variable for `root`.

Configure a `cron` job for the `root` user with something like the following:

```
# Backup nightly at 2am
0 2 * * * /bin/bash -lc '/usr/local/bin/borgsync'

# Verify the backups once a month
40 17 23 * * /usr/local/bin/borgsync -b check
```

For further details on scheduling Borg backups with `cron`, see [cron/README.md](cron/README.md) and the [example crontab entry](cron/crontab.in).

### Automated backups using systemd

Copy the example systemd [unit files](systemd/) to `/etc/systemd/system/`.

Issue the following commands to enable and start the systemd timers:

```bash
sudo systemctl enable borgsync-backup.timer
sudo systemctl enable borgsync-verify.timer

sudo systemctl start borgsync-backup.timer
sudo systemctl start borgsync-verify.timer
```

The included systemd files are set up using a daily schedule. If you want to take backups more often than that you can change the `Timer` parameters directly in the systemd timer files:

```bash
sudo systemctl edit borgsync-backup.timer
```

Here is an example where you run a backup 4 times a day (every 6 hours). See the manual for systemd.timer for more information on the `OnCalendar` format.

```
    [Timer]
    OnCalendar=00/6:00
    RandomizedDelaySec=0
```

The output will land in

```
/etc/systemd/system/borgsync-backup.timer.d/override.conf
```

You can just drop files in the directory directly too, without editing via systemctl. This is better suited for configuration management systems.

You can view the backup logs with:

```bash
journalctl -xu borgsync-backup
journalctl -xu borgsync-verify
```

If you want to run the tasks manually outside the timers you can just start them like usual services:

```bash
sudo systemctl start borgsync-backup
sudo systemctl start borgsync-verify
```

## Examples

### Initialize a backup repository

```bash
# Initialize the default borg repository
borgsync -b init
# Initialize the 'home' borg repository
borgsync -b init -t home
```

### Create a remote backup

```bash
borgsync -b create
# This is the default action without arguments as well
borgsync
```

### Create a remote backup using the `home` custom configuration

```bash
borgsync -b create -t home
```

### Get info about a remote backup repository/archive

```bash
# Info for default borg repository
borgsync -b info
# Info for 'home' borg repository
borgsync -b info -t home
# List contents of default borg repository
borgsync -b list
# List contents of a borg repository archive
borgsync -a example.com-2024-01-28T10:17:40 -b list
```

### Mount a remote backup repository on /mnt/borg

```bash
borgsync -b mount
```

### Upload a folder to the default configured storage service

```bash
borgsync Videos
```

### Verify backups

```bash
    borgsync -b check
```

### Display the command to extract the latest successful archive in the default repository

```bash
borgsync -b extract
```

### Display command to extract `/home/jane` from the latest archive in the `home` repository

```bash
borgsync -b extract -t home /home/jane
```

### Run a command on the default configured storage service

For example, to execute the `ls` command on your configured `rsync.net` account:

```bash
    borgsync -c 'ls */backups'
```

Any supported command can be run similarly:

```bash
    borgsync -c '<command-name> <arguments>'
```

## Borg server preparation

***Server-side configuration is not necessary if using rsync.net or BorgBase***

Install borg and then:

```bash
sudo adduser --system --group --shell /bin/bash borg
sudo mkdir /srv/borg
sudo chown borg. /srv/borg
sudo chmod 755 /srv/borg
```

Generate the needed passwordless ssh-keys as root (the user you run the backup as) on the client

```bash
sudo ssh-keygen
```

Copy the content of the generated public key from `/root/.ssh/<key>.pub` to `/home/borg/.ssh/authorized_keys` on the server, with some restrictions so it looks something like this:

```
    command="borg serve --restrict-to-path /srv/borg/<hostname>",no-pty,no-agent-forwarding,no-port-forwarding,no-X11-forwarding,no-user-rc ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDeCInOLjv0hgzI0u1b/p4yYnCEV5n89HIXF1hrLor+ZQ7lSUii21tpn47Aw8RJJAjfDCwCdQ27MXjpzNelBf4KrlAiN1K3FcnGGIiE3XFNoj4LW7oAjzjFgOKC/ea/hXaCI6E8M/Pn5+MhdNN1ZsWNm/9Zp0+jza+l74DQgOE33XhSBjckUchqtBci7BqoCejy2lVvboFA231mSEpPValcKmG2qaNphAkCgAPjtDOx3V6DGQ8e7jfA2McQYxfju6HlpWPUx/li6VJhRa5huczfJ3J/sdfu123s/lgTW4rG5QNng1vt1FOIZ/TkaEsPt2wzD2Qxdwo70qVts3hrd+r root@client
```
## See also

- [What-is-cloud-computing](what-is-cloud-computing.md)
- [Provider/civo](provider/civo.md)
- [Provider/cloud-provider-comparison](provider/cloud-provider-comparison.md)
- [Rclone Cloud Storage](rclone.md)
  - [Rclone Manual](rclone-manual.md)
