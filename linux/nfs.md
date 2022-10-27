# NFS

Network File System (NFS) is a distributed file system protocol originally developed by Sun Microsystems (Sun), available in **[Linux](linux.md)**, allowing a user on a client computer to access files over a computer network much like local storage is accessed. NFS, like many other protocols, builds on the Open Network Computing Remote Procedure Call (ONC RPC) system. NFS is an open IETF standard defined in a Request for Comments (RFC), allowing anyone to implement the protocol.

---

## Install NFS

Different packages are required for the client and server. Examples below use packages and commands for Ubuntu Linux. Similar commands and packages are available for all Linux distributions.

### Server

```bash
sudo apt -y update
sudo apt -y install nfs-kernel-server
```

### Client

```shell
sudo apt -y update
sudo apt -y install nfs-common
```

## Server Configuration

### Configure NFS Shares

On the server edit `/etc/exports` and add a line for each NFS export. For example:

```shell
/u -mapall=501 -network 10.0.1.0 -mask 255.255.255.0
/home/doctorwhen -rw -network 10.0.1.0 -mask 255.255.255.0
```

After editing `/etc/exports` run `exportfs -a`

### List Exports

On the NFS server run `showmount -e` to list exports:

```shell
showmount -e

Exports list on localhost:
/home/doctorwhen                   10.0.1.0
/u                                 10.0.1.0
```

### Show Clients

On the NFS server run `showmount` to see mounting clients:

```shell
showmount 

Hosts on localhost:
ubuntu.hsd1.ca.comcast.net
```

### List Protocols/Services

To list local services run:

```shell
rpcinfo -p

       program vers proto   port  service
        100000    4   tcp    111  portmapper
        100000    3   tcp    111  portmapper
        100000    2   tcp    111  portmapper
        100000    4   udp    111  portmapper
        100000    3   udp    111  portmapper
        100000    2   udp    111  portmapper
        100024    1   udp  48555  status
        100024    1   tcp  49225  status
        100003    2   tcp   2049  nfs
        100003    3   tcp   2049  nfs
        100003    4   tcp   2049  nfs
        100227    2   tcp   2049
        100227    3   tcp   2049
        100003    2   udp   2049  nfs
        100003    3   udp   2049  nfs
        100003    4   udp   2049  nfs
        100227    2   udp   2049
        100227    3   udp   2049
        100021    1   udp  51841  nlockmgr
        100021    3   udp  51841  nlockmgr
        100021    4   udp  51841  nlockmgr
        100021    1   tcp  37319  nlockmgr
        100021    3   tcp  37319  nlockmgr
        100021    4   tcp  37319  nlockmgr
        100005    1   udp  57376  mountd
        100005    1   tcp  37565  mountd
        100005    2   udp  36255  mountd
        100005    2   tcp  36682  mountd
        100005    3   udp  54897  mountd
        100005    3   tcp  51122  mountd
```

Above output is from an NFS server. You can also run it for remote servers by passing an IP. NFS clients usually just run status and portmapper:

```shell
rpcinfo -p 10.1.0.15

       program vers proto   port  service
        100000    4   tcp    111  portmapper
        100000    3   tcp    111  portmapper
        100000    2   tcp    111  portmapper
        100000    4   udp    111  portmapper
        100000    3   udp    111  portmapper
        100000    2   udp    111  portmapper
        100024    1   udp  44152  status
        100024    1   tcp  53182  status
```

### NFSv4

#### Mounting NFSv4 Shares

The difference in mounting is that you need to provide "nfs4" and transport and port options like this:

```bash
mount -t nfs4 -o proto=tcp,port=2049 server:/export/home /mnt
```

#### Ensure Running Id Mapper

When using NFSv4 share ensure to have the id mapper running on all clients. On Debian you need to explicitely start it:

```bash
service idmapd start
```

#### Mapping Users

You might want to set useful NFSv4 default mappings and some explicit mappings for unknown users:

```bash
cat /etc/idmapd.conf

    [...]
    [Mapping]
    Nobody-User = nobody
    Nobody-Group = nogroup

    [Static]
    someuser@otherserver = localuser
```

### Tuning NFS Server

For the exported filesystem mount options:

-   Use "noatime"
-   Use "async" if you can (risk of data corruption)
-   Use "no\_subtree\_check"

Other than that:

-   Use CFQ I/O scheduler
-   Increase /sys/block/sda/device/block/sda/queue/max\_sectors\_kb
-   Check /sys/block/sda/device/block/sda/queue/read\_ahead\_kb
-   Increase number of nfsd threads

### Getting NFS Statistics

Use "nfsstat" for detailed NFS statistics. The options are "-c" for client and "-s" for server statistics. On the server caching statistics are most interesting:

```bash
nfsstat -o rc

    Server reply cache:
    hits       misses     nocache
    0          63619      885550  
```

On the client errors and retries may be of more interest. Also note that you can get live per-interval results when running with "--sleep=\<interval\>". For example:

```bash
nfsstat -o fh --sleep=2
```

## Client Configuration

### Create mount points

Create directories on which to mount the NFS shares. For example:

```bash
sudo mkdir /mnt/u
```

### Add NFS mounts to /etc/fstab

Edit `/etc/fstab` and add an entry for each NFS mount. For example:

```
10.0.1.22:/u    /mnt/u   nfs auto,nofail,noatime,nolock,intr,tcp,actimeo=1800 0 0
```
### Tuning NFS Clients

When optimizing for performance try the following client mount option
changes:

-   Use "hard" instead of "soft"
-   Add "intr" to allow for dead server and killable client programs
-   Increase "mtu" to maximum
-   Increase "rsize" and "wsize" to maximum supported by clients and server
-   Remove "sync"

After changing and remounting check for effective options using "nfsstat -m" which will give you a list like this:

```bash
nfsstat -m

    /data from 10.1.0.16:/data
     Flags: rw,relatime,vers=4.0,rsize=1048576,wsize=1048576,namlen=255,hard,proto=tcp,port=0,timeo=600,retrans=2,sec=sys,clientaddr=10.1.0.16,local_lock=none,addr=10.1.0.15
```

When synchronous shares are important try the "noac" mount option.

### root rw permissions

Note the **root_squash** mount option. This option is set by default and must be disabled if not wanted.
*Fix:* enable `no_root_squash`in the `/etc/exports` file and reload the permissions with `sudo exportfs -ra`

## See also

- [IPtables](iptables.md)
- [Linux](linux.md)
- [Linux basics](linuxbasics.md)
- [Mount](mount.md)
- [Sudo](sudo.md)
- [UFW](ufw.md)
