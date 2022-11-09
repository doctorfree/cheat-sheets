# rsync-icloud-to-obsidian.sh

```shell
#!/bin/bash
#
# This script will rsync a directory (presumably an Obsidian Vault in iCloud)
# to a locally specified directory.
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
	echo "!		If not an absolute path, will be used as the name of your Vault in iCloud)"
	echo "!		If it is an absolute path, that will be used. (useful for testing)"
	echo "! "
	echo "! dest_dir - Directory to rsync to."
	echo "! "
	echo "! "
	exit 1
fi

SRC=$1
SRC_ICLOUD=""
DEST=$2
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

if [[ "${SRC}" == "/"* ]]
then
	# If there's a leading slash, just use that path
	echo "# Leading slash found in source ${SRC}, not using iCloud..."
	true

else
	if [[ "${SRC}" == *"/"* ]]
	then

		if [[ "${SRC}" != *"/" ]]
		then
			echo "! "
			echo "! Slash found in source ${SRC}!"
			echo "! "
			echo "! Bailing out, as this is coming from iCloud and should be a single directory name."
			echo "! "
			exit 1
		fi
	fi

	SRC=${ICLOUD}/${SRC}
	SRC_ICLOUD=1

fi

#
# Add a slash on the end which means "copy the CONTENTS of this directory and not the directory itself".
# Thanks to https://stackoverflow.com/a/31278462/196073 for helping me sort this out.
#
SRC="${SRC}/"

#
# If destination isn't an absolute path, make it one
#
if [[ "${DEST}" != "/"* ]]
then
	DEST="$(pwd)/${DEST}"
fi

echo "# "
echo "# Starting READ-ONLY sync..."
echo "# "
echo "# Src: ${SRC}"
echo "# Dest: ${DEST}"
echo "# "

rsync -av --delete "${SRC}" "${DEST}"

echo "# "
echo "# Rsync complete!"

#
# Get filtered versions of our source and destination for the alias name
#
ALIAS_SRC=$(basename "${SRC}" | sed -e "s/[^A-Za-z0-9_]/_/g")
ALIAS_DEST=$(basename "${DEST}" | sed -e "s/[^A-Za-z0-9_]/_/g")
ALIAS_NAME="sync-from-icloud-to-${ALIAS_DEST}"


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
echo "# NOTE: This sync was READ-ONLY.  That is intentional because if all files have not"
echo "# yet been copied to iCloud, I don't want you to lose data."
echo "# "

echo "# Done!"

```

## See also

- [CODE_OF_CONDUCT](CODE_OF_CONDUCT.md)
- [create-test-dir.sh](create-test-dir.sh.md)
- [LICENSE](LICENSE.md)
- [README](README.md)
- [rsync-obsidian-to-icloud.sh](rsync-obsidian-to-icloud.sh.md)
