# README

![](../../assets/obsidian-logo.png)

## Rsync Obsidian Vaults to iCloud

The mobile app for <a href="https://obsidian.md/">Obsidian</a> for the iPhone
can write Vaults to iCloud, but getting vaults from your Mac into iCloud can be tricky.
These scripts seek to address that.

## Usage

### Prerequisites

- Make sure you've installed Obsidian on your iPhone FIRST, as it needs to set up an Obsidian directory in iCloud
- Seriously, THIS IS MANDATORY.  If you have not installed Obsidian on your iPhone, STOP NOW and do that.
- You can verify that Obsidian is on your iPhone because it will create a directory in your iCloud account. Here's how to view the contents of that directory on your Mac:
   - `ls -l "Library/Mobile Documents/iCloud~md~obsidian/Documents/"`

The reason for having Obsidian create the directory is that there is some metadata involved with the directory creation.  Therefore, creating the above mentioned directory yourself won't work.


### Getting your Vault into iCloud

- Next, run the script as follows: `[./rsync-obsidian-to-icloud.sh](rsync-obsidian-to-icloud.sh) ./VAULTNAME VAULTNAME_IN_ICLOUD`
- The script will run `rsync` against the local directory that you specify and copy those files to the directory in the Obsidian directory in iCloud
- At the completion of the script, a suggested alias will be printed so that future invocations of the script can be made no matter what directory you're in at the time.


### Syncing changes from iCloud to your Vault

- Run the companion script: `[./rsync-icloud-to-obsidian.sh](rsync-icloud-to-obsidian.sh) VAULTNAME_IN_ICLOUD VAULTNAME`
- This will sync down changes from iCloud to your local vault
- Files that you deleted on iCloud will not be deleted from your local vault, to prevent accidental deletions.
- At the completion of the script, a suggested alias will be printed so that future invocations of the script can be made no matter what directory you're in at the time.


## Caveats

- Depending on how much data you have, it can take a macroscopic amount of time for files from the iCloud directory on your Mac to sync to your iPhone.  You may need to be patient.
- Very large Vaults can crash the Obsidian client.  This has been reported to the devs and is being actively looked into.


## Testing instructions

- Run `create-test-dir.sh` to create some test directories in `test-src/`
- Run a few tests
  - `./rsync-obsidian-to-icloud.sh ./test-src/ /tmp/test` - Should succeed
  - `./rsync-obsidian-to-icloud.sh ./test-src/ test/test2` - Should fail due to slash present
  - `./rsync-obsidian-to-icloud.sh ./test-src/ $(pwd)/test-dest` - Should sync to `./test-dest/`.
  - `./rsync-obsidian-to-icloud.sh ./test-src/ test-dest` - Should sync to `test-dest` in iCloud and be visible via iPhone Obsidian app.

## Who built this? / Contact

My name is Douglas Muth, and I am a software engineer in Philadelphia, PA.

There are several ways to get in touch with me:
- Email to doug.muth AT gmail DOT com or dmuth AT dmuth DOT org
- [Facebook](https://facebook.com/dmuth) and [Twitter](http://twitter.com/dmuth)
- [LinkedIn](https://linkedin.com/in/dmuth)

Feel free to reach out to me if you have any comments, suggestions, or bug reports.


## See also

- [CODE_OF_CONDUCT](CODE_OF_CONDUCT.md)
- [create-test-dir.sh](create-test-dir.sh.md)
- [LICENSE](LICENSE.md)
- [rsync-icloud-to-obsidian.sh](rsync-icloud-to-obsidian.sh.md)
- [rsync-obsidian-to-icloud.sh](rsync-obsidian-to-icloud.sh.md)
