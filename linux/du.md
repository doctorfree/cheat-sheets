# du

**du** (abbreviated from disk usage) is a standard Unix program used to estimate file space usage - space used under a particular directory or files on a file system.
---

## Example usage

With 'root' privileges, use `du`, `sort`, and `head` to display a list of
the top 20 space-consuming files in whichever storage medium '/' is mounted.

Here, `du` is using the `-x` flag to keep to the one filesystem, which is
important for getting accurate results on the filesystem on which you
might, for example, be needing to free space.

In order to sort the human-readable file sizes, `sort` is using the `-h`
flag, the `-k` flag to specify the column to sort (first), and its using
the `-r` flag to reverse the sorting, so we see the highest size first.

To then show the top-20 lines, we use `head` and specify the number of lines
via the `-n` flag. The default number of lines displayed by `head` and
`tail` is 10.

Root privileges are gained for this task by using `sudo` on `bash` in order
to have a new root-owned BASH session, which then executes the commands
proceeding the `-c` flag.

```shell
sudo bash -c 'du -xh / | sort -rhk 1 | head -n 20'
```

Similarly, to see the 20 largest markdown files in subdirectories of the current working directory:

```shell
du -sh */*.md | sort -h | tail -n 20
```

Display just the total human-readable size of the current working directory.

```shell
du -sh
```

Display the total human-readable size of the three provided directories, as
well as the grand total of the combined directories.

```shell
du -chs ~/Desktop ~/Pictures ~/Videos
```

You could potentially make this task a bit easier with BASH brace expansion.

```shell
du -chs ~/{Desktop,Pictures,Videos}
```
