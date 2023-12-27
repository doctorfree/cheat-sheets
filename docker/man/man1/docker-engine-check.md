# NAME

docker-engine-check - Check for available engine updates

# SYNOPSIS

**docker engine check \[OPTIONS\]**

# DESCRIPTION

Check for available engine updates

# OPTIONS

**--containerd**="" override default location of containerd endpoint

**--downgrades**\[=false\] Report downgrades (default omits older versions)

**--engine-image**="" Specify engine image (default uses the same image as currently running)

**--format**="" Pretty-print updates using a Go template

**-h**, **--help**\[=false\] help for check

**--pre-releases**\[=false\] Include pre-release versions

**-q**, **--quiet**\[=false\] Only display available versions

**--registry-prefix**="docker.io/store/docker" Override the existing location where engine images are pulled

**--upgrades**\[=true\] Report available upgrades

# SEE ALSO

**docker-engine(1)**
