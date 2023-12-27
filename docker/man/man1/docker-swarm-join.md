# NAME

docker-swarm-join - Join a swarm as a node and/or manager

# SYNOPSIS

**docker swarm join \[OPTIONS\] HOST:PORT**

# DESCRIPTION

Join a swarm as a node and/or manager

# OPTIONS

**--advertise-addr**="" Advertised address (format: &lt;ip|interface&gt;\[:port\])

**--availability**="active" Availability of the node ("active"|"pause"|"drain")

**--data-path-addr**="" Address or interface to use for data path traffic (format: &lt;ip|interface&gt;)

**-h**, **--help**\[=false\] help for join

**--listen-addr**=0.0.0.0:2377 Listen address (format: &lt;ip|interface&gt;\[:port\])

**--token**="" Token for entry into the swarm

# SEE ALSO

**docker-swarm(1)**
