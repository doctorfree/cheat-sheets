# NAME

docker-container-unpause - Unpause all processes within one or more containers

# SYNOPSIS

**docker container unpause CONTAINER \[CONTAINER...\]**

# DESCRIPTION

The `docker container unpause` command un-suspends all processes in a container. On Linux, it does this using the freezer cgroup.

See the freezer cgroup documentation ⟨https://www.kernel.org/doc/Documentation/cgroup-v1/freezer-subsystem.txt⟩ for further details.

# OPTIONS

**-h**, **--help**\[=false\] help for unpause

# SEE ALSO

**docker-container(1)**
