# NAME

docker-image-history - Show the history of an image

# SYNOPSIS

**docker image history \[OPTIONS\] IMAGE**

# DESCRIPTION

Show the history of when and how an image was created.

# EXAMPLES

>     $ docker history fedora
>     IMAGE          CREATED          CREATED BY                                      SIZE                COMMENT
>     105182bb5e8b   5 days ago       /bin/sh -c #(nop) ADD file:71356d2ad59aa3119d   372.7 MB
>     73bd853d2ea5   13 days ago      /bin/sh -c #(nop) MAINTAINER Lokesh Mandvekar   0 B
>     511136ea3c5a   10 months ago                                                    0 B                 Imported from -

# Display comments in the image history

The `docker commit` command has a **-m** flag for adding comments to the image. These comments will be displayed in the image history.

>     $ sudo docker history docker:scm
>     IMAGE               CREATED             CREATED BY                                      SIZE                COMMENT
>     2ac9d1098bf1        3 months ago        /bin/bash                                       241.4 MB            Added Apache to Fedora base image
>     88b42ffd1f7c        5 months ago        /bin/sh -c #(nop) ADD file:1fd8d7f9f6557cafc7   373.7 MB            
>     c69cab00d6ef        5 months ago        /bin/sh -c #(nop) MAINTAINER Lokesh Mandvekar   0 B                 
>     511136ea3c5a        19 months ago                                                       0 B                 Imported from -

## Format the output

The formatting option (`--format`) will pretty-prints history output using a Go template.

Valid placeholders for the Go template are listed below:

<table>
<tbody>
<tr class="odd">
<td style="text-align: left;"><code>Placeholder</code></td>
<td style="text-align: left;"><code>Description</code></td>
</tr>
<tr class="even">
<td style="text-align: left;"><code>.ID</code></td>
<td style="text-align: left;">Image ID</td>
</tr>
<tr class="odd">
<td style="text-align: left;"><code>.CreatedSince</code></td>
<td style="text-align: left;">Elapsed time since the image was created if <code>--human=true</code>, otherwise timestamp of when image was created</td>
</tr>
<tr class="even">
<td style="text-align: left;"><code>.CreatedAt</code></td>
<td style="text-align: left;">Timestamp of when image was created</td>
</tr>
<tr class="odd">
<td style="text-align: left;"><code>.CreatedBy</code></td>
<td style="text-align: left;">Command that was used to create the image</td>
</tr>
<tr class="even">
<td style="text-align: left;"><code>.Size</code></td>
<td style="text-align: left;">Image disk size</td>
</tr>
<tr class="odd">
<td style="text-align: left;"><code>.Comment</code></td>
<td style="text-align: left;">Comment for image</td>
</tr>
</tbody>
</table>

When using the `--format` option, the `history` command will either output the data exactly as the template declares or, when using the `table` directive, will include column headers as well.

The following example uses a template without headers and outputs the `ID` and `CreatedSince` entries separated by a colon for all images:

>     $ docker images --format "{{.ID}}: {{.CreatedSince}} ago"
>
>     cc1b61406712: 2 weeks ago
>     <missing>: 2 weeks ago
>     <missing>: 2 weeks ago
>     <missing>: 2 weeks ago
>     <missing>: 2 weeks ago
>     <missing>: 3 weeks ago
>     <missing>: 3 weeks ago
>     <missing>: 3 weeks ago

# OPTIONS

**--format**="" Pretty-print images using a Go template

**-h**, **--help**\[=false\] help for history

**-H**, **--human**\[=true\] Print sizes and dates in human readable format

**--no-trunc**\[=false\] Don't truncate output

**-q**, **--quiet**\[=false\] Only show numeric IDs

# SEE ALSO

**docker-image(1)**
