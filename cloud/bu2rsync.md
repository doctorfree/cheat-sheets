The `bu2rsync` command can be used to manage cloud storage on [rsync.net](https://www.rsync.net). It also supports remote backups using the [borg](https://www.borgbackup.org) deduplicating archiver with compression and encryption.

In order to use `bu2rsync` an `rsync.net` account is required.

## Download

`bu2rsync` can be downloaded at https://github.com/doctorfree/DoctorFreeScripts/blob/master/scripts/bu2rsync.sh

A companion utility, `borg-create`, is available at https://github.com/doctorfree/DoctorFreeScripts/blob/master/scripts/borg-create.sh

## Usage

```
Usage: bu2rsync [-b borg-command] [-c command] [-d dir] [-lL] [-n]
                [-q|Q] [-r] [-u] [-U user] [-H host] [-v] folder
Where:
	-b 'init' initializes a borg backup system on rsync.net
	-b 'check' verifies the consistency of the borg backup repository
	-b 'create' creates a borg backup to rsync.net
	-b 'info' displays detailed information about the borg backup repository
	-b 'list' lists all archives in the borg backup repository
	-b 'mount' mounts the borg backup repository on /mnt/borg
	-b 'umount' unmounts the borg backup repository from /mnt/borg
	-c 'command' runs 'command' on rsync.net
	-d 'dir' specifies a borg backup directory (default: 'backups'
	-l indicates list the contents of the backup folder
	-L indicates recursively list the contents of the backup folder
	-n indicates perform a dry run, don't make any changes
	-q indicates see how much space your account uses with the quota/df commands
	-Q indicates see how much space your account uses with the quota/df/du commands
	-r indicates remove remote backup
	-v indicates verbose mode
	-U 'user' sets the rsync.net user to 'user'
	-H 'host' sets the rsync.net host to 'host'
	-u displays this usage message and exits

The 'folder' argument indicates the folder to sync/list/remove with rsync.net
```

## Automate daily remote backups

To automate daily remote backups with the `borg-create` script, verify that the `root` user can access the `rsync.net` account using `ssh` without being prompted. Copy the `$HOME/.config/borg/` folder to `/root/.config/borg/` and set the `BORG_PASSPHRASE` environment variable for `root`.

Configure a `cron` job for the `root` user with something like the following:

```
0 2 * * * /bin/bash -lc '/path/to/borg-create'
```

The above will run `borg-create` as the `root` user every night at 2am.

## Examples

### Initialize a backup repository

```bash
bu2rsync -b init
```

### Create a remote backup

```bash
bu2rsync -b create
```

### Get info about a remote backup repository

```bash
bu2rsync -b info
bu2rsync -b list
```

### Mount a remote backup repository on /mnt/borg

```bash
bu2rsync -b mount
```

### Upload a folder to rsync.net

```bash
bu2rsync Videos
```

## See also

- [What-is-cloud-computing](what-is-cloud-computing.md)
- [Provider/civo](provider/civo.md)
- [Provider/cloud-provider-comparison](provider/cloud-provider-comparison.md)
- [Rclone Cloud Storage](rclone.md)
  - [Rclone Manual](rclone-manual.md)
