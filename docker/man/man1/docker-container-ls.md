# NAME

docker-container-ls - List containers

# SYNOPSIS

**docker container ls \[OPTIONS\]**

# DESCRIPTION

List the containers in the local repository. By default this shows only the running containers.

# Filters

Filter output based on these conditions: - ancestor=(&lt;image-name&gt;\[:tag\]|&lt;image-id&gt;| ⟨image@digest⟩) containers created from an image or a descendant. - before=(&lt;container-name&gt;|&lt;container-id&gt;) - expose=(&lt;port&gt;\[/&lt;proto&gt;\]|&lt;startport-endport&gt;/\[&lt;proto&gt;\]) - exited=&lt;int&gt; an exit code of &lt;int&gt; - health=(starting|healthy|unhealthy|none) - id=&lt;ID&gt; a container's ID - isolation=(`default`|`process`|`hyperv`) (Windows daemon only) - is-task=(true|false) - label=&lt;key&gt; or label=&lt;key&gt;=&lt;value&gt; - name=&lt;string&gt; a container's name - network=(&lt;network-id&gt;|&lt;network-name&gt;) - publish=(&lt;port&gt;\[/&lt;proto&gt;\]|&lt;startport-endport&gt;/\[&lt;proto&gt;\]) - since=(&lt;container-name&gt;|&lt;container-id&gt;) - status=(created|restarting|removing|running|paused|exited) - volume=(&lt;volume name&gt;|&lt;mount point destination&gt;)

# Format

The formatting option (**--format**) pretty-prints container output using a Go template.

Valid placeholders for the Go template are listed below: - .ID - Container ID. - .Image - Image ID. - .Command - Quoted command. - .CreatedAt - Time when the container was created. - .RunningFor - Elapsed time since the container was started. - .Ports - Exposed ports. - .Status - Container status. - .Size - Container disk size. - .Names - Container names. - .Labels - All labels assigned to the container. - .Label - Value of a specific label for this container. For example **'{{.Label "com.docker.swarm.cpu"}}'**. - .Mounts - Names of the volumes mounted in this container. - .Networks - Names of the networks attached to this container.

# EXAMPLES

# Display all containers, including non-running

>     $ docker container ls -a
>     CONTAINER ID        IMAGE                 COMMAND                CREATED             STATUS      PORTS    NAMES
>     a87ecb4f327c        fedora:20             /bin/sh -c #(nop) MA   20 minutes ago      Exit 0               desperate_brattain
>     01946d9d34d8        vpavlin/rhel7:latest  /bin/sh -c #(nop) MA   33 minutes ago      Exit 0               thirsty_bell
>     c1d3b0166030        acffc0358b9e          /bin/sh -c yum -y up   2 weeks ago         Exit 1               determined_torvalds
>     41d50ecd2f57        fedora:20             /bin/sh -c #(nop) MA   2 weeks ago         Exit 0               drunk_pike

# Display only IDs of all containers, including non-running

>     $ docker container ls -a -q
>     a87ecb4f327c
>     01946d9d34d8
>     c1d3b0166030
>     41d50ecd2f57

# Display only IDs of all containers that have the name `determined_torvalds`

>     $ docker container ls -a -q --filter=name=determined_torvalds
>     c1d3b0166030

# Display containers with their commands

>     $ docker container ls --format "{{.ID}}: {{.Command}}"
>     a87ecb4f327c: /bin/sh -c #(nop) MA
>     01946d9d34d8: /bin/sh -c #(nop) MA
>     c1d3b0166030: /bin/sh -c yum -y up
>     41d50ecd2f57: /bin/sh -c #(nop) MA

# Display containers with their labels in a table

>     $ docker container ls --format "table {{.ID}}\t{{.Labels}}"
>     CONTAINER ID        LABELS
>     a87ecb4f327c        com.docker.swarm.node=ubuntu,com.docker.swarm.storage=ssd
>     01946d9d34d8
>     c1d3b0166030        com.docker.swarm.node=debian,com.docker.swarm.cpu=6
>     41d50ecd2f57        com.docker.swarm.node=fedora,com.docker.swarm.cpu=3,com.docker.swarm.storage=ssd

# Display containers with their node label in a table

>     $ docker container ls --format 'table {{.ID}}\t{{(.Label "com.docker.swarm.node")}}'
>     CONTAINER ID        NODE
>     a87ecb4f327c        ubuntu
>     01946d9d34d8
>     c1d3b0166030        debian
>     41d50ecd2f57        fedora

# Display containers with `remote-volume` mounted

>     $ docker container ls --filter volume=remote-volume --format "table {{.ID}}\t{{.Mounts}}"
>     CONTAINER ID        MOUNTS
>     9c3527ed70ce        remote-volume

# Display containers with a volume mounted in `/data`

>     $ docker container ls --filter volume=/data --format "table {{.ID}}\t{{.Mounts}}"
>     CONTAINER ID        MOUNTS
>     9c3527ed70ce        remote-volume

# Display containers that have published port of 80:

>     $ docker ps --filter publish=80
>     CONTAINER ID        IMAGE               COMMAND             CREATED              STATUS              PORTS                   NAMES
>     fc7e477723b7        busybox             "top"               About a minute ago   Up About a minute   0.0.0.0:32768->80/tcp   admiring_roentgen

# Display containers that have exposed TCP port in the range of `8000-8080`:

>     $ docker ps --filter expose=8000-8080/tcp
>     CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
>     9833437217a5        busybox             "top"               21 seconds ago      Up 19 seconds       8080/tcp            dreamy_mccarthy

# OPTIONS

**-a**, **--all**\[=false\] Show all containers (default shows just running)

**-f**, **--filter**= Filter output based on conditions provided

**--format**="" Pretty-print containers using a Go template

**-h**, **--help**\[=false\] help for ls

**-n**, **--last**=-1 Show n last created containers (includes all states)

**-l**, **--latest**\[=false\] Show the latest created container (includes all states)

**--no-trunc**\[=false\] Don't truncate output

**-q**, **--quiet**\[=false\] Only display numeric IDs

**-s**, **--size**\[=false\] Display total file sizes

# SEE ALSO

**docker-container(1)**
