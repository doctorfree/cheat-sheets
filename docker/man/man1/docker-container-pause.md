# NAME

docker-container-pause - Pause all processes within one or more containers

# SYNOPSIS

**docker container pause CONTAINER \[CONTAINER...\]**

# DESCRIPTION

The `docker container pause` command suspends all processes in the specified containers. On Linux, this uses the freezer cgroup. Traditionally, when suspending a process the `SIGSTOP` signal is used, which is observable by the process being suspended. With the freezer cgroup the process is unaware, and unable to capture, that it is being suspended, and subsequently resumed. On Windows, only Hyper-V containers can be paused.

See the freezer cgroup documentation ⟨https://www.kernel.org/doc/Documentation/cgroup-v1/freezer-subsystem.txt⟩ for further details.

**docker-container-unpause(1)** to unpause all processes within a container.

# OPTIONS

**-h**, **--help**\[=false\] help for pause

# SEE ALSO

**docker-container(1)**
