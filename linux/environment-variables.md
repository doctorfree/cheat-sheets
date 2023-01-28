# Environment Variables in Linux

An environment variable is a dynamic-named value that can affect the way running processes will behave on a computer. Environment variables are part of the environment in which a process runs. For example, a running process can query the value of the `TEMP` environment variable to discover a suitable location to store temporary files, or the `HOME` or `USERPROFILE` variable to find the directory structure owned by the user running the process.

They were introduced in their modern form in 1979 with Version 7 Unix, so are included in all Unix operating system flavors and variants from that point onward including Linux and macOS. From PC DOS 2.0 in 1982, all succeeding Microsoft operating systems, including Microsoft Windows, and OS/2 also have included them as a feature, although with somewhat different syntax, usage and standard variable names.

## Examples

Examples of environment variables include:

- [**PATH**](https://en.wikipedia.org/wiki/PATH_(variable)): a list of directory paths. When the user types a command without providing the full path, this list is checked to see whether it contains a path that leads to the command.
- **HOME** (Unix-like) and `USERPROFILE` (Microsoft Windows): indicate where a user's [home directory](https://en.wikipedia.org/wiki/Home_directory) is located in the [file system](https://en.wikipedia.org/wiki/File_system).
- **HOME/{.AppName}** (Unix-like) and `APPDATA\{DeveloperName\AppName}` (Microsoft Windows): for storing application settings. Many applications incorrectly use `USERPROFILE` for application settings in Windows: `USERPROFILE` should only be used in dialogs that allow user to choose between paths like Documents/Pictures/Downloads/Music; for programmatic purposes, `APPDATA` (for roaming application settings shared across multiple devices), `LOCALAPPDATA` (for local application settings) or `PROGRAMDATA` (for application settings shared between multiple OS users) should be used.[4]
- **TERM** (Unix-like): specifies the type of computer terminal or terminal emulator being used (e.g., vt100 or dumb).
- **PS1** (Unix-like): specifies how the prompt is displayed in the Bourne shell and variants.
- **MAIL** (Unix-like): used to indicate where a user's mail is to be found.
- **TEMP**: location where processes can store temporary files.

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

* _**/etc/bash.bashrc**_: This file is read whenever a `bash` interactive shell is started (normal terminal) and all the commands specified in here are executed.
* _**/etc/zsh/zshrc**_: This file is read whenever a `zsh` interactive shell is started (normal terminal) and all the commands specified in here are executed.
* _**/etc/profile** and **/etc/profile.d/\***_: This file is read every time a user logs in. Thus all the commands executed in here will execute only once at the time of user logging in.
  *   \*\*Example: \*\*

      `/etc/profile.d/somescript.sh`

      ```shell
      #!/bin/bash
      TEST=$(cat /var/somefile)
      export $TEST
      ```

### Files that affect behavior for only a specific user

* **~/.bashrc** : This file behaves the same way `/etc/bash.bashrc` file works but it is executed only for a specific user. If you want to create an environment for yourself go ahead and modify or create this file in your home directory.
* **~/.zshrc** : This file behaves the same way `/etc/zsh/zshrc` file works but it is executed only for a specific user. If you want to create an environment for yourself go ahead and modify or create this file in your home directory.
* **~/.profile, \~/.bash\_profile, \~/.bash\_login** : These files are same as `/etc/profile`. The difference comes in the way it is executed. This file is executed only when a user in whose home directory this file exists, logs in.

## Common variables

* **DISPLAY** - the display used by **X**. This variable is usually set to **:0.0**, which means the first display on the current computer.
* **EDITOR** - the user's preferred text editor.
* **HISTFILESIZE** - the maximum number of lines contained in the history file.
* **HISTSIZE** - Number of lines added to the history file when the user finish his session
* **HOME** - your home directory.
* **HOSTNAME** - the hostname of the computer.
* **LANG** - your current language.
* **MAIL** - the location of the user's mail spool. Usually **/var/spool/mail/USER**.
* **MANPATH** - the list of directories to search for manual pages.
* **OSTYPE** - the type of operating system.
* **PS1** - the default prompt in bash.
* **PATH** - stores the path of all the directories which holds binary files you want to execute just by specifying the name of the file and not by relative or absolute path.
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

Example **PS1** settings in `~/.bashrc`:

- Prompt with color
    ```shell
    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u\[\033[00m\] \w:\[\033[00m\] \$ '
    ```
- Prompt without color
    ```shell
    PS1='${debian_chroot:+($debian_chroot)}\u \w: \$ '
    ```
- Typical prompt for `xterm`
    ```shell
    PS1="\[\e]0;\w\a\]$PS1"
    ```
- Prompt with hostname and conditional status
    ```shell
    PS1='\@ \u@`/bin/hostname`:`pwd` # '
    if [ -f /var/run/infos/status.file ]; then
      PS1='\@ \u@`/bin/hostname` $myip [$(cat /var/run/infos/status.file | cut -d":" -f1)] `pwd` # '
    else
      PS1='\@ \u@`/bin/hostname` $myip  `pwd` # '
    fi
    ```
