# NAME

docker-context-update - Update a context

# SYNOPSIS

**docker context update \[OPTIONS\] CONTEXT**

# DESCRIPTION

Update a context

Docker endpoint config:

NAME DESCRIPTION from Copy named context's Docker endpoint configuration host Docker endpoint on which to connect ca Trust certs signed only by this CA cert Path to TLS certificate file key Path to TLS key file skip-tls-verify Skip TLS certificate validation

Kubernetes endpoint config:

NAME DESCRIPTION from Copy named context's Kubernetes endpoint configuration config-file Path to a Kubernetes config file context-override Overrides the context set in the kubernetes config file namespace-override Overrides the namespace set in the kubernetes config file

Example:

$ docker context update my-context --description "some description" --docker "host=tcp://myserver:2376,ca= /ca-file,cert= /cert-file,key= /key-file"

# OPTIONS

**--default-stack-orchestrator**="" Default orchestrator for stack operations to use with this context (swarm|kubernetes|all)

**--description**="" Description of the context

**--docker**=\[\] set the docker endpoint

**-h**, **--help**\[=false\] help for update

**--kubernetes**=\[\] set the kubernetes endpoint

# SEE ALSO

**docker-context(1)**
