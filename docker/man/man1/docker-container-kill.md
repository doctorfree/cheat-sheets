# NAME

docker-container-kill - Kill one or more running containers

# SYNOPSIS

**docker container kill \[OPTIONS\] CONTAINER \[CONTAINER...\]**

# DESCRIPTION

The main process inside each container specified will be sent SIGKILL, or any signal specified with option --signal.

# OPTIONS

**-h**, **--help**\[=false\] help for kill

**-s**, **--signal**="KILL" Signal to send to the container

# SEE ALSO

**docker-container(1)**
