# NAME

docker-service-logs - Fetch the logs of a service or task

# SYNOPSIS

**docker service logs \[OPTIONS\] SERVICE|TASK**

# DESCRIPTION

Fetch the logs of a service or task

# OPTIONS

**--details**\[=false\] Show extra details provided to logs

**-f**, **--follow**\[=false\] Follow log output

**-h**, **--help**\[=false\] help for logs

**--no-resolve**\[=false\] Do not map IDs to Names in output

**--no-task-ids**\[=false\] Do not include task IDs in output

**--no-trunc**\[=false\] Do not truncate output

**--raw**\[=false\] Do not neatly format logs

**--since**="" Show logs since timestamp (e.g. 2013-01-02T13:23:37) or relative (e.g. 42m for 42 minutes)

**--tail**="all" Number of lines to show from the end of the logs

**-t**, **--timestamps**\[=false\] Show timestamps

# SEE ALSO

**docker-service(1)**
