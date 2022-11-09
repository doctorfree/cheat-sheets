# rsync-obsidian-to-icloud.sh

```shell
#!/bin/bash
#
# This script will rsync a directory (presumably an Obsidian Vault) to the iCloud Obsidian directory
#

# Errors are fatal
set -e

ICLOUD="$HOME/Library/Mobile Documents/iCloud~md~obsidian/Documents"

if test ! "$2"
then
	echo "! "
	echo "! Syntax: $0 src_dir dest_dir"
	echo "! "
	echo "! src_dir - The directory to rsync from"
	echo "! "
	echo "! dest_dir - Directory to rsync to."
	echo "!		If not an absolute path, will be placed under the Obsidian folder"
	echo "!			(So basically the name of your Vault in iCloud)"
	echo "! "
	echo "!		If it is an absolute path, that will be used. (useful for testing)"
	echo "! "
	exit 1
fi

SRC=$1
DEST=$2
DEST_ICLOUD=""
SRC_ORIG=$1
DEST_ORIG=$2

if test ! -d "${ICLOUD}"
then
	echo "! "
	echo "! Obsidian directory (${ICLOUD}) not found in iCloud folder"
	echo "! "
	echo "! Make sure you run the Obsidian mobile app FIRST, so the directory shows up."
	echo "! "
	exit 1
fi


if [[ "${DEST}" == "/"* ]]
then
	# If there's a leading slash, just use that path
	echo "# Leading slash found in destinaton ${DEST}, not using iCloud..."
	true

else
	if [[ "${DEST}" == *"/"* ]]
	then

		if [[ "${DEST}" != *"/" ]]
		then
			echo "! "
			echo "! Slash found in destination ${DEST}!"
			echo "! "
			echo "! Bailing out, as this is going in iCloud and should be a single directory name."
			echo "! "
			exit 1
		fi
	fi

	DEST=${ICLOUD}/${DEST}
	DEST_ICLOUD=1

fi

#
# Add a slash on the end which means "copy the CONTENTS of this directory and not the directory itself".
# Thanks to https://stackoverflow.com/a/31278462/196073 for helping me sort this out.
#
SRC="${SRC}/"

#
# If source isn't an absolute path, make it one
#
if [[ "${SRC}" != "/"* ]]
then
	SRC="$(pwd)/${SRC}"
fi

echo "# "
echo "# Starting sync..."
echo "# "
echo "# Src: ${SRC}"
echo "# Dest: ${DEST}"
echo "# "

#
# Exclude syncing ZIP files because we already have them in Dropbox.
#
rsync -av --exclude '*zip' --delete "${SRC}" "${DEST}"


echo "# "
echo "# Rsync complete!"

#
# Get filtered versions of our source and destination for the alias name
#
ALIAS_SRC=$(basename "${SRC}" | sed -e "s/[^A-Za-z0-9_]/_/g")
ALIAS_DEST=$(basename "${DEST}" | sed -e "s/[^A-Za-z0-9_]/_/g")
ALIAS_NAME="sync-to-icloud-from-${ALIAS_SRC}"


#
# Print instructions on how to set an alias to do this exact same sync for future use.
#
echo "# "
echo "# To create an alias so that you can run this command in the future from your filesystem,"
echo "#	put this in \$HOME/.bashrc:"
echo "# "
echo "alias ${ALIAS_NAME}='$(pwd)/$0 \"${SRC}\" \"${DEST}\"'"
echo "# "
echo "# Yes, I know that's a long alias, but you can use tab-autocomplete for it. :-)"
echo "# "

echo "# Done!"

```

## See also

- [CODE_OF_CONDUCT](CODE_OF_CONDUCT.md)
- [create-test-dir.sh](create-test-dir.sh.md)
- [LICENSE](LICENSE.md)
- [README](README.md)
- [rsync-icloud-to-obsidian.sh](rsync-icloud-to-obsidian.sh.md)
