# NAME

docker-service-create - Create a new service

# SYNOPSIS

**docker service create \[OPTIONS\] IMAGE \[COMMAND\] \[ARG...\]**

# DESCRIPTION

Create a new service

# OPTIONS

**--config**= Specify configurations to expose to the service

**--constraint**= Placement constraints

**--container-label**= Container labels

**--credential-spec**= Credential spec for managed service account (Windows only)

**-d**, **--detach**\[=false\] Exit immediately instead of waiting for the service to converge

**--dns**= Set custom DNS servers

**--dns-option**= Set DNS options

**--dns-search**= Set custom DNS search domains

**--endpoint-mode**="vip" Endpoint mode (vip or dnsrr)

**--entrypoint**= Overwrite the default ENTRYPOINT of the image

**-e**, **--env**= Set environment variables

**--env-file**= Read in a file of environment variables

**--generic-resource**= User defined resources

**--group**= Set one or more supplementary user groups for the container

**--health-cmd**="" Command to run to check health

**--health-interval**= Time between running the check (ms|s|m|h)

**--health-retries**=0 Consecutive failures needed to report unhealthy

**--health-start-period**= Start period for the container to initialize before counting retries towards unstable (ms|s|m|h)

**--health-timeout**= Maximum time to allow one check to run (ms|s|m|h)

**-h**, **--help**\[=false\] help for create

**--host**= Set one or more custom host-to-IP mappings (host:ip)

**--hostname**="" Container hostname

**--init**\[=false\] Use an init inside each service container to forward signals and reap processes

**--isolation**="" Service container isolation mode

**-l**, **--label**= Service labels

**--limit-cpu**= Limit CPUs

**--limit-memory**=0 Limit Memory

**--log-driver**="" Logging driver for service

**--log-opt**= Logging driver options

**--mode**="replicated" Service mode (replicated or global)

**--mount**= Attach a filesystem mount to the service

**--name**="" Service name

**--network**= Network attachments

**--no-healthcheck**\[=false\] Disable any container-specified HEALTHCHECK

**--no-resolve-image**\[=false\] Do not query the registry to resolve image digest and supported platforms

**--placement-pref**= Add a placement preference

**-p**, **--publish**= Publish a port as a node port

**-q**, **--quiet**\[=false\] Suppress progress output

**--read-only**\[=false\] Mount the container's root filesystem as read only

**--replicas**= Number of tasks

**--replicas-max-per-node**=0 Maximum number of tasks per node (default 0 = unlimited)

**--reserve-cpu**= Reserve CPUs

**--reserve-memory**=0 Reserve Memory

**--restart-condition**="" Restart when condition is met ("none"|"on-failure"|"any") (default "any")

**--restart-delay**= Delay between restart attempts (ns|us|ms|s|m|h) (default 5s)

**--restart-max-attempts**= Maximum number of restarts before giving up

**--restart-window**= Window used to evaluate the restart policy (ns|us|ms|s|m|h)

**--rollback-delay**=0s Delay between task rollbacks (ns|us|ms|s|m|h) (default 0s)

**--rollback-failure-action**="" Action on rollback failure ("pause"|"continue") (default "pause")

**--rollback-max-failure-ratio**=0 Failure rate to tolerate during a rollback (default 0)

**--rollback-monitor**=0s Duration after each task rollback to monitor for failure (ns|us|ms|s|m|h) (default 5s)

**--rollback-order**="" Rollback order ("start-first"|"stop-first") (default "stop-first")

**--rollback-parallelism**=1 Maximum number of tasks rolled back simultaneously (0 to roll back all at once)

**--secret**= Specify secrets to expose to the service

**--stop-grace-period**= Time to wait before force killing a container (ns|us|ms|s|m|h) (default 10s)

**--stop-signal**="" Signal to stop the container

**--sysctl**= Sysctl options

**-t**, **--tty**\[=false\] Allocate a pseudo-TTY

**--update-delay**=0s Delay between updates (ns|us|ms|s|m|h) (default 0s)

**--update-failure-action**="" Action on update failure ("pause"|"continue"|"rollback") (default "pause")

**--update-max-failure-ratio**=0 Failure rate to tolerate during an update (default 0)

**--update-monitor**=0s Duration after each task update to monitor for failure (ns|us|ms|s|m|h) (default 5s)

**--update-order**="" Update order ("start-first"|"stop-first") (default "stop-first")

**--update-parallelism**=1 Maximum number of tasks updated simultaneously (0 to update all at once)

**-u**, **--user**="" Username or UID (format: &lt;name|uid&gt;\[:&lt;group|gid&gt;\])

**--with-registry-auth**\[=false\] Send registry authentication details to swarm agents

**-w**, **--workdir**="" Working directory inside the container

# SEE ALSO

**docker-service(1)**
