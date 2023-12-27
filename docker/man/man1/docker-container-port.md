# NAME

docker-container-port - List port mappings or a specific mapping for the container

# SYNOPSIS

**docker container port CONTAINER \[PRIVATE\_PORT\[/PROTO\]\]**

# DESCRIPTION

List port mappings for the CONTAINER, or lookup the public-facing port that is NAT-ed to the PRIVATE\_PORT

# EXAMPLES

>     $ docker ps
>     CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS                                            NAMES
>     b650456536c7        busybox:latest      top                 54 minutes ago      Up 54 minutes       0.0.0.0:1234->9876/tcp, 0.0.0.0:4321->7890/tcp   test

# Find out all the ports mapped

>     $ docker container port test
>     7890/tcp -> 0.0.0.0:4321
>     9876/tcp -> 0.0.0.0:1234

# Find out a specific mapping

>     $ docker container port test 7890/tcp
>     0.0.0.0:4321
>
>     $ docker container port test 7890
>     0.0.0.0:4321

# An example showing error for non-existent mapping

>     $ docker container port test 7890/udp
>     2014/06/24 11:53:36 Error: No public port '7890/udp' published for test

# OPTIONS

**-h**, **--help**\[=false\] help for port

# SEE ALSO

**docker-container(1)**
