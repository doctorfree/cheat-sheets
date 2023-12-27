# NAME

docker-swarm-ca - Display and rotate the root CA

# SYNOPSIS

**docker swarm ca \[OPTIONS\]**

# DESCRIPTION

Display and rotate the root CA

# OPTIONS

**--ca-cert**= Path to the PEM-formatted root CA certificate to use for the new cluster

**--ca-key**= Path to the PEM-formatted root CA key to use for the new cluster

**--cert-expiry**=2160h0m0s Validity period for node certificates (ns|us|ms|s|m|h)

**-d**, **--detach**\[=false\] Exit immediately instead of waiting for the root rotation to converge

**--external-ca**= Specifications of one or more certificate signing endpoints

**-h**, **--help**\[=false\] help for ca

**-q**, **--quiet**\[=false\] Suppress progress output

**--rotate**\[=false\] Rotate the swarm CA - if no certificate or key are provided, new ones will be generated

# SEE ALSO

**docker-swarm(1)**
