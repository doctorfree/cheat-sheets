# NAME

docker-swarm-init - Initialize a swarm

# SYNOPSIS

**docker swarm init \[OPTIONS\]**

# DESCRIPTION

Initialize a swarm

# OPTIONS

**--advertise-addr**="" Advertised address (format: &lt;ip|interface&gt;\[:port\])

**--autolock**\[=false\] Enable manager autolocking (requiring an unlock key to start a stopped manager)

**--availability**="active" Availability of the node ("active"|"pause"|"drain")

**--cert-expiry**=2160h0m0s Validity period for node certificates (ns|us|ms|s|m|h)

**--data-path-addr**="" Address or interface to use for data path traffic (format: &lt;ip|interface&gt;)

**--data-path-port**=0 Port number to use for data path traffic (1024 - 49151). If no value is set or is set to 0, the default port (4789) is used.

**--default-addr-pool**=\[\] default address pool in CIDR format

**--default-addr-pool-mask-length**=24 default address pool subnet mask length

**--dispatcher-heartbeat**=5s Dispatcher heartbeat period (ns|us|ms|s|m|h)

**--external-ca**= Specifications of one or more certificate signing endpoints

**--force-new-cluster**\[=false\] Force create a new cluster from current state

**-h**, **--help**\[=false\] help for init

**--listen-addr**=0.0.0.0:2377 Listen address (format: &lt;ip|interface&gt;\[:port\])

**--max-snapshots**=0 Number of additional Raft snapshots to retain

**--snapshot-interval**=10000 Number of log entries between Raft snapshots

**--task-history-limit**=5 Task history retention limit

# SEE ALSO

**docker-swarm(1)**
