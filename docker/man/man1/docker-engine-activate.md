# NAME

docker-engine-activate - Activate Enterprise Edition

# SYNOPSIS

**docker engine activate \[OPTIONS\]**

# DESCRIPTION

Activate Enterprise Edition.

With this command you may apply an existing Docker enterprise license, or interactively download one from Docker. In the interactive exchange, you can sign up for a new trial, or download an existing license. If you are currently running a Community Edition engine, the daemon will be updated to the Enterprise Edition Docker engine with additional capabilities and long term support.

For more information about different Docker Enterprise license types visit

⟨https://www.docker.com/licenses⟩

For non-interactive scriptable deployments, download your license from

⟨https://hub.docker.com/⟩ then specify the file with the '--license' flag.

# OPTIONS

**--containerd**="" override default location of containerd endpoint

**--display-only**\[=false\] only display license information and exit

**--engine-image**="" Specify engine image

**--format**="" Pretty-print licenses using a Go template

**-h**, **--help**\[=false\] help for activate

**--license**="" License File

**--quiet**\[=false\] Only display available licenses by ID

**--registry-prefix**="docker.io/store/docker" Override the default location where engine images are pulled

**--version**="" Specify engine version (default is to use currently running version)

# SEE ALSO

**docker-engine(1)**
