# NAME

docker-service-update - Update a service

# SYNOPSIS

**docker service update \[OPTIONS\] SERVICE**

# DESCRIPTION

Update a service

# OPTIONS

**--args**= Service command args

**--config-add**= Add or update a config file on a service

**--config-rm**= Remove a configuration file

**--constraint-add**= Add or update a placement constraint

**--constraint-rm**= Remove a constraint

**--container-label-add**= Add or update a container label

**--container-label-rm**= Remove a container label by its key

**--credential-spec**= Credential spec for managed service account (Windows only)

**-d**, **--detach**\[=false\] Exit immediately instead of waiting for the service to converge

**--dns-add**= Add or update a custom DNS server

**--dns-option-add**= Add or update a DNS option

**--dns-option-rm**= Remove a DNS option

**--dns-rm**= Remove a custom DNS server

**--dns-search-add**= Add or update a custom DNS search domain

**--dns-search-rm**= Remove a DNS search domain

**--endpoint-mode**="" Endpoint mode (vip or dnsrr)

**--entrypoint**= Overwrite the default ENTRYPOINT of the image

**--env-add**= Add or update an environment variable

**--env-rm**= Remove an environment variable

**--force**\[=false\] Force update even if no changes require it

**--generic-resource-add**= Add a Generic resource

**--generic-resource-rm**= Remove a Generic resource

**--group-add**= Add an additional supplementary user group to the container

**--group-rm**= Remove a previously added supplementary user group from the container

**--health-cmd**="" Command to run to check health

**--health-interval**= Time between running the check (ms|s|m|h)

**--health-retries**=0 Consecutive failures needed to report unhealthy

**--health-start-period**= Start period for the container to initialize before counting retries towards unstable (ms|s|m|h)

**--health-timeout**= Maximum time to allow one check to run (ms|s|m|h)

**-h**, **--help**\[=false\] help for update

**--host-add**= Add a custom host-to-IP mapping (host:ip)

**--host-rm**= Remove a custom host-to-IP mapping (host:ip)

**--hostname**="" Container hostname

**--image**="" Service image tag

**--init**\[=false\] Use an init inside each service container to forward signals and reap processes

**--isolation**="" Service container isolation mode

**--label-add**= Add or update a service label

**--label-rm**= Remove a label by its key

**--limit-cpu**= Limit CPUs

**--limit-memory**=0 Limit Memory

**--log-driver**="" Logging driver for service

**--log-opt**= Logging driver options

**--mount-add**= Add or update a mount on a service

**--mount-rm**= Remove a mount by its target path

**--network-add**= Add a network

**--network-rm**= Remove a network

**--no-healthcheck**\[=false\] Disable any container-specified HEALTHCHECK

**--no-resolve-image**\[=false\] Do not query the registry to resolve image digest and supported platforms

**--placement-pref-add**= Add a placement preference

**--placement-pref-rm**= Remove a placement preference

**--publish-add**= Add or update a published port

**--publish-rm**= Remove a published port by its target port

**-q**, **--quiet**\[=false\] Suppress progress output

**--read-only**\[=false\] Mount the container's root filesystem as read only

**--replicas**= Number of tasks

**--replicas-max-per-node**=0 Maximum number of tasks per node (default 0 = unlimited)

**--reserve-cpu**= Reserve CPUs

**--reserve-memory**=0 Reserve Memory

**--restart-condition**="" Restart when condition is met ("none"|"on-failure"|"any")

**--restart-delay**= Delay between restart attempts (ns|us|ms|s|m|h)

**--restart-max-attempts**= Maximum number of restarts before giving up

**--restart-window**= Window used to evaluate the restart policy (ns|us|ms|s|m|h)

**--rollback**\[=false\] Rollback to previous specification

**--rollback-delay**=0s Delay between task rollbacks (ns|us|ms|s|m|h)

**--rollback-failure-action**="" Action on rollback failure ("pause"|"continue")

**--rollback-max-failure-ratio**=0 Failure rate to tolerate during a rollback

**--rollback-monitor**=0s Duration after each task rollback to monitor for failure (ns|us|ms|s|m|h)

**--rollback-order**="" Rollback order ("start-first"|"stop-first")

**--rollback-parallelism**=0 Maximum number of tasks rolled back simultaneously (0 to roll back all at once)

**--secret-add**= Add or update a secret on a service

**--secret-rm**= Remove a secret

**--stop-grace-period**= Time to wait before force killing a container (ns|us|ms|s|m|h)

**--stop-signal**="" Signal to stop the container

**--sysctl-add**= Add or update a Sysctl option

**--sysctl-rm**= Remove a Sysctl option

**-t**, **--tty**\[=false\] Allocate a pseudo-TTY

**--update-delay**=0s Delay between updates (ns|us|ms|s|m|h)

**--update-failure-action**="" Action on update failure ("pause"|"continue"|"rollback")

**--update-max-failure-ratio**=0 Failure rate to tolerate during an update

**--update-monitor**=0s Duration after each task update to monitor for failure (ns|us|ms|s|m|h)

**--update-order**="" Update order ("start-first"|"stop-first")

**--update-parallelism**=0 Maximum number of tasks updated simultaneously (0 to update all at once)

**-u**, **--user**="" Username or UID (format: &lt;name|uid&gt;\[:&lt;group|gid&gt;\])

**--with-registry-auth**\[=false\] Send registry authentication details to swarm agents

**-w**, **--workdir**="" Working directory inside the container

# SEE ALSO

**docker-service(1)**
