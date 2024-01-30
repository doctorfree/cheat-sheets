# Borgsync Configuration Specification

This document describes the `borgsync` configuration specification.
The default `borgsync` configuration file is `/etc/borgsync/base`.
Individual users can override this in `~/.config/borgsync/base` or
by specifying an alternate base configuration with the `-C /path/to/config`
command line argument to `borgsync`.

Custom `borgsync` configurations all use the base configuration settings
and override any of these settings. For example, a custom configuration
in `/etc/borgsync/borgbase` would use all of the settings in the base
configuration `/etc/borgsync/base` and override the remote username and
remote hostname, setting them to a BorgBase account. Backups executed
with `borgsync -b create -t borgbase ...` would perform the same backup
as the default base setting but use the BorgBase account instead.

Below are details on each of the supported `borgsync` configuration settings.

## Remote username and hostname

The remote storage service or `ssh` server username and hostname must be
manually configured. This setting can be found in the base config file at
`/etc/borgsync/base` and can be overridden in individual custom configurations.

```bash
REMOTE_USER="<your_remote_user>"
REMOTE_HOST="<your_remote_host>"
```

## Environment variables

If necessary, set and export `BORG_PASSPHRASE` in the environment:

```bash
export BORG_PASSPHRASE="longandcomplexpassphrase"
```

## Absolute path to the locally installed borg command

The `borgsync` installation script installs `borg` in `/usr/local/bin`. If
`borg` is installed in a different location then modify this setting accordingly.

```bash
BORG="/usr/local/bin/borg"
```

## Absolute path to the remote installed borg command

Storage services that support `borg` will already have it installed.
If an alternate location is desired or if you have manually installed
`borg` then specify the absolute path here or in the environment.

```bash
BORG_REMOTE_PATH="/usr/local/bin/borg1/borg1"
```

## Storage path on remote, default: <hostname>/backups

```bash
BACK_HOST="$(hostname)"
BACK_DIR="backups"
```
## Remote borg repository to use

The `BORG_REPO` variable sets the borg repository to use. Multiple repositories
can be configured. This setting distinguishes which repository is used.

On the `BorgBase` storage service use the `ssh://` protocol prefix.

If using a non-standard SSH port `ssh://` has to be specified (per borg v1.0.9).

```bash
BORG_REPO="ssh://${REMOTE_USER}@${REMOTE_HOST}:<ssh_port>/${BACK_HOST}/${BACK_DIR}"
```

On `rsync.net` the `ssh` protocol is assumed and not required:

```bash
BORG_REPO="${REMOTE_USER}@${REMOTE_HOST}:${BACK_HOST}/${BACK_DIR}"
```

## How many backups to keep

```bash
KEEP_HOURLY=0
KEEP_DAILY=7
KEEP_WEEKLY=4
KEEP_MONTHLY=3
KEEP_YEARLY=2
```

## PATHS - which paths are included

The `PATHS` configuration specifies which filesystem paths are included
in a backup. This setting does not support wildcards or regular expressions.
In order to include files and folders using wildcards or regular expressions
see the `INCLUDES` setting below.

```bash
PATHS=(
    '/etc'
    '/home'
    '/root'
    '/srv'
    '/usr/local'
    '/var'
)
```

## EXCLUDES - which files/folders to exclude from the corresponding PATHS

The `EXCLUDES` and `INCLUDES` settings specify patterns to match for
exclusion and inclusion.

```bash
EXCLUDES=(
    '/root/.cache'
    '/home/*/.cache'
    '/home/*/.docker/desktop/vms'
    '/home/*/.local/share/Daedalus'
    '/home/*/.local/share/nvim-*'
    '/home/*/Music/*'
    '/home/*/transfers/*'
    '/var/tmp/*'
    '/var/cache'
    '/var/lib/docker/devicemapper'
    '/var/lib/docker/volumes'
    '/var/lock/*'
    '/var/run/*'
    '/var/tmp/*'
    '/var/backups/*'
    '/var/spool/*'
    '*/.Trash-*'
    '*/[Cc]ache/*'
    '*/.bitcoin/blocks/*'
    '*.vmdk'
    '*.pyc'
)
```

## INCLUDES - patterns to include

```bash
INCLUDES=()
```

## Arguments to the borg commands

```bash
BORG_CREATE_ARGS=(
    --info
    --list
    --filter AME
    --compression lz4
    --exclude-caches
    --one-file-system
    --exclude-if-present '.nobackup'
)
```

## borg prune ...

```bash
BORG_PRUNE_ARGS=(
    --info
    --list
)
```

## borg check ...

```bash
BORG_CHECK_ARGS=(
    --info
)
```

## borg init ...

```bash
BORG_INIT_ARGS=(
   --encryption=repokey-blake2
)
```
