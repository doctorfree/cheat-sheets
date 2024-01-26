The `borgsync` command can be used to manage cloud storage on [rsync.net](https://www.rsync.net). It also supports remote backups using the [borg](https://www.borgbackup.org) deduplicating archiver with compression and encryption.

In order to use `borgsync` an `rsync.net` account is not required but defaults are configured for use with an `rsync.net` account.

## Install

`borgsync` can be installed with the following commands:

```bash
git clone https://github.com/doctorfree/borgsync
cd borgsync
./install
```

## Usage

```
Usage: borgsync [-b init|check|create|delete|info|list|mount|umount]
                [-C config] [-c cmd] [-d dir] [-lLn] [-m mnt] [-U user]
                [-H host] [-qQruv] [-t default|full|home|logs] folder
Where:
	-b 'init' initializes a borg backup system on rsync.net
	-b 'check' verifies the consistency of the borg backup repository
	-b 'create' creates a borg backup to rsync.net
	   combine with '-t default|full|home|logs' (default: default)
	   -t 'default' performs a borg backup of /home /var and /etc
	   -t 'full' performs a full borg backup to rsync.net
	   -t 'home' performs a borg backup of only /home to rsync.net
	   -t 'logs' performs a borg backup of only /var/log to rsync.net
	-b 'delete' deletes the borg backup repository on rsync.net
	-b 'info' displays detailed information about the borg backup repository
	-b 'list' lists all archives in the borg backup repository
	-b 'mount' mounts the borg backup repository on /mnt/borg
	-b 'umount' unmounts the borg backup repository from /mnt/borg
	-C 'config' specifies the config file (default: /etc/borgsync/config)
	-c 'cmd' runs command 'cmd' on rsync.net
	-d 'dir' specifies a borg backup directory (default: 'backups'
	-l indicates list the contents of the backup folder
	-L indicates recursively list the contents of the backup folder
	-m 'mnt' specifies the mount point for the borg repo (default: /mnt/borg)
	-n indicates perform a dry run, don't make any changes
	-q indicates see how much space your account uses with the quota/df commands
	-Q indicates see how much space your account uses with the quota/df/du commands
	-r indicates remove remote backup
	-v indicates verbose mode
	-U 'user' sets the rsync.net user to 'user'
	-H 'host' sets the rsync.net host to 'host'
	-u displays this usage message and exits

The 'folder' argument indicates the folder to sync/list/remove with rsync.net
Without arguments borgsync performs the default borg backup
```

## Automate daily remote backups

To automate daily remote backups with the `borgsync` command, verify that the `root` user can access the `rsync.net` account using `ssh` without being prompted. Copy the `$HOME/.config/borg/` folder to `/root/.config/borg/` and set the `BORG_PASSPHRASE` environment variable for `root`.

Configure a `cron` job for the `root` user with something like the following:

```
0 2 * * * /bin/bash -lc '/path/to/borgsync'
```

The above will run `borgsync` as the `root` user every night at 2am.

## Examples

### Initialize a backup repository

```bash
borgsync -b init
```

### Create a remote backup

```bash
borgsync -b create
```

### Get info about a remote backup repository

```bash
borgsync -b info
borgsync -b list
```

### Mount a remote backup repository on /mnt/borg

```bash
borgsync -b mount
```

### Upload a folder to rsync.net

```bash
borgsync Videos
```

## See also

- [What-is-cloud-computing](what-is-cloud-computing.md)
- [Provider/civo](provider/civo.md)
- [Provider/cloud-provider-comparison](provider/cloud-provider-comparison.md)
- [Rclone Cloud Storage](rclone.md)
  - [Rclone Manual](rclone-manual.md)
