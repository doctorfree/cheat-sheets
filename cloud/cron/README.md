# Borg scheduled backups with cron

To schedule nightly Borg backups using `cron` run the following command:

```bash
sudo crontab crontab.in
```

Note that the above command will overwrite any existing `crontab` entries for `root`.
To preserve existing `crontab` entries, first list them, add them to `crontab.in`,
and run the above command:

```bash
sudo crontab -l >> crontab.in
vi crontab.in # Edit and cleanup comments, duplicates, etc
sudo crontab crontab.in
```
