# Environment Variables in Linux

An environment variable is a dynamic-named value that can affect the way running processes will behave on a computer. Environment variables are part of the environment in which a process runs. For example, a running process can query the value of the `TEMP` environment variable to discover a suitable location to store temporary files, or the `HOME` or `USERPROFILE` variable to find the directory structure owned by the user running the process.

They were introduced in their modern form in 1979 with Version 7 Unix, so are included in all Unix operating system flavors and variants from that point onward including Linux and macOS. From PC DOS 2.0 in 1982, all succeeding Microsoft operating systems, including Microsoft Windows, and OS/2 also have included them as a feature, although with somewhat different syntax, usage and standard variable names.

## Examples

Examples of environment variables include:

- [`PATH`](https://en.wikipedia.org/wiki/PATH_(variable)): a list of directory paths. When the user types a command without providing the full path, this list is checked to see whether it contains a path that leads to the command.
- `HOME` (Unix-like) and `USERPROFILE` (Microsoft Windows): indicate where a user's [home directory](https://en.wikipedia.org/wiki/Home_directory) is located in the [file system](https://en.wikipedia.org/wiki/File_system).
- `HOME/{.AppName}` (Unix-like) and `APPDATA\{DeveloperName\AppName}` (Microsoft Windows): for storing application settings. Many applications incorrectly use `USERPROFILE` for application settings in Windows: `USERPROFILE` should only be used in dialogs that allow user to choose between paths like Documents/Pictures/Downloads/Music; for programmatic purposes, `APPDATA` (for roaming application settings shared across multiple devices), `LOCALAPPDATA` (for local application settings) or `PROGRAMDATA` (for application settings shared between multiple OS users) should be used.[4]
- `TERM` (Unix-like): specifies the type of computer terminal or terminal emulator being used (e.g., vt100 or dumb).
- `PS1` (Unix-like): specifies how the prompt is displayed in the Bourne shell and variants.
- `MAIL` (Unix-like): used to indicate where a user's mail is to be found.
- `TEMP`: location where processes can store temporary files.

## Global variables

The global variables **will be** inherited by **child processes**.

You can create a global variable for your current session doing:

```shell
export MYGLOBAL="hello world"
echo $MYGLOBAL #Prints: hello world
```

This variable will be accessible by your current sessions and its child processes.

You can **remove** a variable doing:

```shell
unset MYGLOBAL
```

## Local variables

The **local variables** can only be **accessed** by the **current shell/script**.

```shell
LOCAL="my local"
echo $LOCAL
unset LOCAL
```

## List current variables

```shell
set
env
printenv
cat /proc/$$/environ
cat /proc/`python -c "import os; print(os.getppid())"`/environ
```

## Persistent Environment variables

### Files that affect behavior of every user

* _**/etc/bash.bashrc**_: This file is read whenever an interactive shell is started (normal terminal) and all the commands specified in here are executed.
* _**/etc/profile and /etc/profile.d/\***_**:** This file is read every time a user logs in. Thus all the commands executed in here will execute only once at the time of user logging in.
  *   \*\*Example: \*\*

      `/etc/profile.d/somescript.sh`

```shell
#!/bin/bash
TEST=$(cat /var/somefile)
export $TEST
```

### Files that affect behavior for only a specific user

* _**\~/.bashrc**_: This file behaves the same way _/etc/bash.bashrc_ file works but it is executed only for a specific user. If you want to create an environment for yourself go ahead and modify or create this file in your home directory.
* _**\~/.profile, \~/.bash\_profile, \~/.bash\_login**_**:** These files are same as _/etc/profile_. The difference comes in the way it is executed. This file is executed only when a user in whose home directory this file exists, logs in.

**Extracted from:** [**here**](https://codeburst.io/linux-environment-variables-53cea0245dc9) **and** [**here**](https://www.gnu.org/software/bash/manual/html\_node/Bash-Startup-Files.html)

## Common variables

* **DISPLAY** - the display used by **X**. This variable is usually set to **:0.0**, which means the first display on the current computer.
* **EDITOR** - the user's preferred text editor.
* **HISTFILESIZE** - the maximum number of lines contained in the history file.
* \*\*HISTSIZE - \*\*Number of lines added to the history file when the user finish his session
* **HOME** - your home directory.
* **HOSTNAME** - the hostname of the computer.
* **LANG** - your current language.
* **MAIL** - the location of the user's mail spool. Usually **/var/spool/mail/USER**.
* **MANPATH** - the list of directories to search for manual pages.
* **OSTYPE** - the type of operating system.
* **PS1** - the default prompt in bash.
* \*\*PATH - \*\*stores the path of all the directories which holds binary files you want to execute just by specifying the name of the file and not by relative or absolute path.
* **PWD** - the current working directory.
* **SHELL** - the path to the current command shell (for example, **/bin/bash**).
* **TERM** - the current terminal type (for example, **xterm**).
* **TZ** - your time zone.
* **USER** - your current username.

## Interesting variables for hacking

### HISTFILESIZE

Change the **value of this variable to 0**, so when you **end your session** the **history file** (\~/.bash\_history) **will be deleted**.

```shell
export HISTFILESIZE=0
```

### HISTSIZE

Change the **value of this variable to 0**, so when you **end your session** any command will be added to the **history file** (\~/.bash\_history).

```shell
export HISTSIZE=0
```

### http\_proxy & https\_proxy

The processes will use the **proxy** declared here to connect to internet through **http or https**.

```shell
export http_proxy="http://10.10.10.10:8080"
export https_proxy="http://10.10.10.10:8080"
```

### SSL\_CERT\_FILE & SSL\_CERT\_DIR

The processes will trust the certificates indicated in **these env variables**.

```shell
export SSL_CERT_FILE=/path/to/ca-bundle.pem
export SSL_CERT_DIR=/path/to/ca-certificates
```

### PS1

Change how your prompt looks.

I have created [**this one**](https://gist.github.com/carlospolop/43f7cd50f3deea972439af3222b68808) (based on another, read the code).

Root:

![](<../.gitbook/assets/image (87).png>)

Regular user:

![](<../.gitbook/assets/image (88).png>)

One, two and three backgrounded jobs:

![](<../.gitbook/assets/image (89).png>)

One background job, one stopped and last command didn't finish correctly:

![](<../.gitbook/assets/image (90).png>)

<details>

<summary><a href="https://www.twitch.tv/hacktricks_live/schedule"><strong>?? HackTricks LIVE Twitch</strong></a> <strong>Wednesdays 5.30pm (UTC) ?? -</strong> <a href="https://www.youtube.com/@hacktricks_LIVE"><strong>? Youtube ?</strong></a></summary>

* Do you work in a **cybersecurity company**? Do you want to see your **company advertised in HackTricks**? or do you want to have access to the **latest version of the PEASS or download HackTricks in PDF**? Check the [**SUBSCRIPTION PLANS**](https://github.com/sponsors/carlospolop)!
* Discover [**The PEASS Family**](https://opensea.io/collection/the-peass-family), our collection of exclusive [**NFTs**](https://opensea.io/collection/the-peass-family)
* Get the [**official PEASS & HackTricks swag**](https://peass.creator-spring.com)
* **Join the** [**?**](https://emojipedia.org/speech-balloon/) [**Discord group**](https://discord.gg/hRep4RUj7f) or the [**telegram group**](https://t.me/peass) or **follow** me on **Twitter** [**?**](https://github.com/carlospolop/hacktricks/tree/7af18b62b3bdc423e11444677a6a73d4043511e9/\[https:/emojipedia.org/bird/README.md)[**@carlospolopm**](https://twitter.com/carlospolopm)**.**
* **Share your hacking tricks by submitting PRs to the** [**hacktricks repo**](https://github.com/carlospolop/hacktricks) **and** [**hacktricks-cloud repo**](https://github.com/carlospolop/hacktricks-cloud).

</details>
