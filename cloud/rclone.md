![Logo dark](https://rclone.org/img/logo_on_dark__horizontal_color.svg)

[Website](https://rclone.org) | [Documentation](https://rclone.org/docs/) | [Download](https://rclone.org/downloads/) | [Changelog](https://rclone.org/changelog/) | [Installation](https://rclone.org/install/) | [Forum](https://forum.rclone.org/) | [Manual](rclone-manual.md)

# Rclone

Rclone *("rsync for cloud storage")* is a command-line program to sync files and directories to and from different cloud storage providers.

  | **Storage** |      |      |      | **Providers** |
  | ----------- | ---- | ---- | ---- | ------------- |
  | [1Fichier](https://rclone.org/fichier/) | [Akamai Netstorage](https://rclone.org/netstorage/) | [Alibaba Cloud (Aliyun) Object Storage System (OSS)](https://rclone.org/s3/#alibaba-oss) | [Amazon Drive](https://rclone.org/amazonclouddrive/) ([See note](https://rclone.org/amazonclouddrive/#status)) | [Amazon S3](https://rclone.org/s3/) |
  | [ArvanCloud Object Storage (AOS)](https://rclone.org/s3/#arvan-cloud-object-storage-aos) | [Backblaze B2](https://rclone.org/b2/) | [Box](https://rclone.org/box/) | [Ceph](https://rclone.org/s3/#ceph) | [China Mobile Ecloud Elastic Object Storage (EOS)](https://rclone.org/s3/#china-mobile-ecloud-eos) |
  | [Cloudflare R2](https://rclone.org/s3/#cloudflare-r2) | [Citrix ShareFile](https://rclone.org/sharefile/) | [DigitalOcean Spaces](https://rclone.org/s3/#digitalocean-spaces) | [Digi Storage](https://rclone.org/koofr/#digi-storage) | [Dreamhost](https://rclone.org/s3/#dreamhost) |
  | [Dropbox](https://rclone.org/dropbox/) | [Enterprise File Fabric](https://rclone.org/filefabric/) | [Fastmail Files](https://rclone.org/webdav/#fastmail-files) | [FTP](https://rclone.org/ftp/) | [Google Cloud Storage](https://rclone.org/googlecloudstorage/) |
  | [Google Drive](https://rclone.org/drive/) | [Google Photos](https://rclone.org/googlephotos/) | [HDFS (Hadoop Distributed Filesystem)](https://rclone.org/hdfs/) | [HiDrive](https://rclone.org/hidrive/) | [HTTP](https://rclone.org/http/) |
  | [Huawei Cloud Object Storage Service(OBS)](https://rclone.org/s3/#huawei-obs) | [Internet Archive](https://rclone.org/internetarchive/) | [Jottacloud](https://rclone.org/jottacloud/) | [IBM COS S3](https://rclone.org/s3/#ibm-cos-s3) | [IONOS Cloud](https://rclone.org/s3/#ionos) |
  | [Koofr](https://rclone.org/koofr/) | [Leviia Object Storage](https://rclone.org/s3/#leviia) | [Liara Object Storage](https://rclone.org/s3/#liara-object-storage) | [Linkbox](https://rclone.org/linkbox) | [Linode Object Storage](https://rclone.org/s3/#linode) |
  | [Mail.ru Cloud](https://rclone.org/mailru/) | [Memset Memstore](https://rclone.org/swift/) | [Mega](https://rclone.org/mega/) | [Memory](https://rclone.org/memory/) | [Microsoft Azure Blob Storage](https://rclone.org/azureblob/) |
  | [Microsoft Azure Files Storage](https://rclone.org/azurefiles/) | [Microsoft OneDrive](https://rclone.org/onedrive/) | [Minio](https://rclone.org/s3/#minio) | [Nextcloud](https://rclone.org/webdav/#nextcloud) | [OVH](https://rclone.org/swift/) |
  | [Blomp Cloud Storage](https://rclone.org/swift/) | [OpenDrive](https://rclone.org/opendrive/) | [OpenStack Swift](https://rclone.org/swift/) | [Oracle Cloud Storage](https://rclone.org/swift/) | [Oracle Object Storage](https://rclone.org/oracleobjectstorage/) |
  | [ownCloud](https://rclone.org/webdav/#owncloud) | [pCloud](https://rclone.org/pcloud/) | [Petabox](https://rclone.org/s3/#petabox) | [PikPak](https://rclone.org/pikpak/) | [premiumize.me](https://rclone.org/premiumizeme/) |
  | [put.io](https://rclone.org/putio/) | [Proton Drive](https://rclone.org/protondrive/) | [QingStor](https://rclone.org/qingstor/) | [Qiniu Cloud Object Storage (Kodo)](https://rclone.org/s3/#qiniu) | [Quatrix](https://rclone.org/quatrix/) |
  | [Rackspace Cloud Files](https://rclone.org/swift/) | [RackCorp Object Storage](https://rclone.org/s3/#RackCorp) | [Scaleway](https://rclone.org/s3/#scaleway) | [Seafile](https://rclone.org/seafile/) | [SeaweedFS](https://rclone.org/s3/#seaweedfs) |
  | [SFTP](https://rclone.org/sftp/) | [SMB / CIFS](https://rclone.org/smb/) | [StackPath](https://rclone.org/s3/#stackpath) | [Storj](https://rclone.org/storj/) | [SugarSync](https://rclone.org/sugarsync/) |
  | [Synology C2 Object Storage](https://rclone.org/s3/#synology-c2) | [Tencent Cloud Object Storage (COS)](https://rclone.org/s3/#tencent-cos) | [Wasabi](https://rclone.org/s3/#wasabi) | [WebDAV](https://rclone.org/webdav/) | [Yandex Disk](https://rclone.org/yandex/) |
  | | [Zoho WorkDrive](https://rclone.org/zoho/) | | [The local filesystem](https://rclone.org/local/) | |

Please see [the full list of all storage providers and their features](https://rclone.org/overview/)

### Virtual storage providers

These backends adapt or modify other storage providers

  * [Alias](https://rclone.org/alias/) : rename existing remotes
  * [Cache](https://rclone.org/cache/) : cache remotes (DEPRECATED)
  * [Chunker](https://rclone.org/chunker/) : split large files
  * [Combine](https://rclone.org/combine/) : combine multiple remotes into a directory tree
  * [Compress](https://rclone.org/compress/) : compress files
  * [Crypt](https://rclone.org/crypt/) : encrypt files
  * [Hasher](https://rclone.org/hasher/) : hash files
  * [Union](https://rclone.org/union/) : join multiple remotes to work together

## Features

  * MD5/SHA-1 hashes checked at all times for file integrity
  * Timestamps preserved on files
  * Partial syncs supported on a whole file basis
  * [Copy](https://rclone.org/commands/rclone_copy/) mode to just copy new/changed files
  * [Sync](https://rclone.org/commands/rclone_sync/) (one way) mode to make a directory identical
  * [Check](https://rclone.org/commands/rclone_check/) mode to check for file hash equality
  * Can sync to and from network, e.g. two different cloud accounts
  * Optional large file chunking ([Chunker](https://rclone.org/chunker/))
  * Optional transparent compression ([Compress](https://rclone.org/compress/))
  * Optional encryption ([Crypt](https://rclone.org/crypt/))
  * Optional FUSE mount ([rclone mount](https://rclone.org/commands/rclone_mount/))
  * Multi-threaded downloads to local disk
  * Can [serve](https://rclone.org/commands/rclone_serve/) local or remote files over HTTP/WebDAV/FTP/SFTP/DLNA

## Installation & documentation

Please see the [rclone website](https://rclone.org/) for:

  * [Installation](https://rclone.org/install/)
  * [Documentation & configuration](https://rclone.org/docs/)
  * [Changelog](https://rclone.org/changelog/)
  * [FAQ](https://rclone.org/faq/)
  * [Storage providers](https://rclone.org/overview/)
  * [Forum](https://forum.rclone.org/)
  * ...and more

## Downloads

  * https://rclone.org/downloads/

License
-------

This is free software under the terms of the MIT license
