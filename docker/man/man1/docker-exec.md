# NAME

docker-exec - Run a command in a running container

# SYNOPSIS

**docker exec \[OPTIONS\] CONTAINER COMMAND \[ARG...\]**

# DESCRIPTION

Alias for `docker container exec`.

# OPTIONS

**-d**, **--detach**\[=false\] Detached mode: run command in the background

**--detach-keys**="" Override the key sequence for detaching a container

**-e**, **--env**= Set environment variables

**-h**, **--help**\[=false\] help for exec

**-i**, **--interactive**\[=false\] Keep STDIN open even if not attached

**--privileged**\[=false\] Give extended privileges to the command

**-t**, **--tty**\[=false\] Allocate a pseudo-TTY

**-u**, **--user**="" Username or UID (format: &lt;name|uid&gt;\[:&lt;group|gid&gt;\])

**-w**, **--workdir**="" Working directory inside the container

# SEE ALSO

**docker(1)**
