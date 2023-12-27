# NAME

docker-container-top - Display the running processes of a container

# SYNOPSIS

**docker container top CONTAINER \[ps OPTIONS\]**

# DESCRIPTION

Display the running process of the container. ps-OPTION can be any of the options you would pass to a Linux ps command.

All displayed information is from host's point of view.

# EXAMPLES

Run **docker container top** with the ps option of -x:

>     $ docker container top 8601afda2b -x
>     PID      TTY       STAT       TIME         COMMAND
>     16623    ?         Ss         0:00         sleep 99999

# OPTIONS

**-h**, **--help**\[=false\] help for top

# SEE ALSO

**docker-container(1)**
