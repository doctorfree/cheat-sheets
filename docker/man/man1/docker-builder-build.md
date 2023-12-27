# NAME

docker-builder-build - Build an image from a Dockerfile

# SYNOPSIS

**docker builder build \[OPTIONS\] PATH | URL | -**

# DESCRIPTION

Build an image from a Dockerfile

# OPTIONS

**--add-host**= Add a custom host-to-IP mapping (host:ip)

**--build-arg**= Set build-time variables

**--cache-from**=\[\] Images to consider as cache sources

**--cgroup-parent**="" Optional parent cgroup for the container

**--compress**\[=false\] Compress the build context using gzip

**--cpu-period**=0 Limit the CPU CFS (Completely Fair Scheduler) period

**--cpu-quota**=0 Limit the CPU CFS (Completely Fair Scheduler) quota

**-c**, **--cpu-shares**=0 CPU shares (relative weight)

**--cpuset-cpus**="" CPUs in which to allow execution (0-3, 0,1)

**--cpuset-mems**="" MEMs in which to allow execution (0-3, 0,1)

**--disable-content-trust**\[=true\] Skip image verification

**-f**, **--file**="" Name of the Dockerfile (Default is 'PATH/Dockerfile')

**--force-rm**\[=false\] Always remove intermediate containers

**-h**, **--help**\[=false\] help for build

**--iidfile**="" Write the image ID to the file

**--isolation**="" Container isolation technology

**--label**= Set metadata for an image

**-m**, **--memory**=0 Memory limit

**--memory-swap**=0 Swap limit equal to memory plus swap: '-1' to enable unlimited swap

**--network**="default" Set the networking mode for the RUN instructions during build

**--no-cache**\[=false\] Do not use cache when building the image

**-o**, **--output**=\[\] Output destination (format: type=local,dest=path)

**--platform**="" Set platform if server is multi-platform capable

**--progress**="auto" Set type of progress output (auto, plain, tty). Use plain to show container output

**--pull**\[=false\] Always attempt to pull a newer version of the image

**-q**, **--quiet**\[=false\] Suppress the build output and print image ID on success

**--rm**\[=true\] Remove intermediate containers after a successful build

**--secret**=\[\] Secret file to expose to the build (only if BuildKit enabled): id=mysecret,src=/local/secret

**--security-opt**=\[\] Security options

**--shm-size**=0 Size of /dev/shm

**--squash**\[=false\] Squash newly built layers into a single new layer

**--ssh**=\[\] SSH agent socket or keys to expose to the build (only if BuildKit enabled) (format: default|&lt;id&gt;\[=&lt;socket&gt;|&lt;key&gt;\[,&lt;key&gt;\]\])

**--stream**\[=false\] Stream attaches to server to negotiate build context

**-t**, **--tag**= Name and optionally a tag in the 'name:tag' format

**--target**="" Set the target build stage to build.

**--ulimit**=\[\] Ulimit options

# SEE ALSO

**docker-builder(1)**
