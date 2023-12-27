# NAME

docker-volume-rm - Remove one or more volumes

# SYNOPSIS

**docker volume rm \[OPTIONS\] VOLUME \[VOLUME...\]**

# DESCRIPTION

Remove one or more volumes. You cannot remove a volume that is in use by a container.

# OPTIONS

**-f**, **--force**\[=false\] Force the removal of one or more volumes

**-h**, **--help**\[=false\] help for rm

# EXAMPLE

>
>     $ docker volume rm hello
>     hello

# SEE ALSO

**docker-volume(1)**
