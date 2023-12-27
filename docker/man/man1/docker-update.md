# NAME

docker-update - Update configuration of one or more containers

# SYNOPSIS

**docker update \[OPTIONS\] CONTAINER \[CONTAINER...\]**

# DESCRIPTION

Alias for `docker container update`.

# OPTIONS

**--blkio-weight**=0 Block IO (relative weight), between 10 and 1000, or 0 to disable (default 0)

**--cpu-period**=0 Limit CPU CFS (Completely Fair Scheduler) period

**--cpu-quota**=0 Limit CPU CFS (Completely Fair Scheduler) quota

**--cpu-rt-period**=0 Limit the CPU real-time period in microseconds

**--cpu-rt-runtime**=0 Limit the CPU real-time runtime in microseconds

**-c**, **--cpu-shares**=0 CPU shares (relative weight)

**--cpus**= Number of CPUs

**--cpuset-cpus**="" CPUs in which to allow execution (0-3, 0,1)

**--cpuset-mems**="" MEMs in which to allow execution (0-3, 0,1)

**-h**, **--help**\[=false\] help for update

**--kernel-memory**=0 Kernel memory limit

**-m**, **--memory**=0 Memory limit

**--memory-reservation**=0 Memory soft limit

**--memory-swap**=0 Swap limit equal to memory plus swap: '-1' to enable unlimited swap

**--pids-limit**=0 Tune container pids limit (set -1 for unlimited)

**--restart**="" Restart policy to apply when a container exits

# SEE ALSO

**docker(1)**
