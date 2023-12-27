# NAME

docker-container-diff - Inspect changes to files or directories on a container's filesystem

# SYNOPSIS

**docker container diff CONTAINER**

# DESCRIPTION

List the changed files and directories in a container᾿s filesystem since the container was created. Three different types of change are tracked:

<table>
<tbody>
<tr class="odd">
<td style="text-align: left;"><code>Symbol</code></td>
<td style="text-align: left;"><code>Description</code></td>
</tr>
<tr class="even">
<td style="text-align: left;"><code>A</code></td>
<td style="text-align: left;">A file or directory was added</td>
</tr>
<tr class="odd">
<td style="text-align: left;"><code>D</code></td>
<td style="text-align: left;">A file or directory was deleted</td>
</tr>
<tr class="even">
<td style="text-align: left;"><code>C</code></td>
<td style="text-align: left;">A file or directory was changed</td>
</tr>
</tbody>
</table>

You can use the full or shortened container ID or the container name set using **docker run --name** option.

# EXAMPLES

Inspect the changes to an `nginx` container:

>     $ docker diff 1fdfd1f54c1b
>
>     C /dev
>     C /dev/console
>     C /dev/core
>     C /dev/stdout
>     C /dev/fd
>     C /dev/ptmx
>     C /dev/stderr
>     C /dev/stdin
>     C /run
>     A /run/nginx.pid
>     C /var/lib/nginx/tmp
>     A /var/lib/nginx/tmp/client_body
>     A /var/lib/nginx/tmp/fastcgi
>     A /var/lib/nginx/tmp/proxy
>     A /var/lib/nginx/tmp/scgi
>     A /var/lib/nginx/tmp/uwsgi
>     C /var/log/nginx
>     A /var/log/nginx/access.log
>     A /var/log/nginx/error.log

# OPTIONS

**-h**, **--help**\[=false\] help for diff

# SEE ALSO

**docker-container(1)**
