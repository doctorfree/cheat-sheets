![HashiCorp Packer logo](assets/logo-packer-padded.svg)

Packer is a tool for building identical machine images for multiple platforms
from a single source configuration.

Packer is lightweight, runs on every major operating system, and is highly
performant, creating machine images for multiple platforms in parallel. Packer
comes out of the box with support for many platforms, the full list of which can
be found at https://www.packer.io/docs/builders.

Support for other platforms can be added via plugins.

The images that Packer creates can easily be turned into
[Vagrant](http://www.vagrantup.com) boxes.

Project Homepage: https://www.packer.io

Documentation: https://developer.hashicorp.com/packer/docs

Plugins: https://developer.hashicorp.com/packer/plugins 

---

## Installation

### macOS

```shell
brew tap hashicorp/tap
brew install hashicorp/tap/packer
```

### Windows

https://developer.hashicorp.com/packer/downloads

### Linux

#### Arch Linux

```shell
sudo pacman -S packer
```

#### Ubuntu/Debian

```shell
wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor | sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list

sudo apt update && sudo apt install packer
```


---
## Plugins

TODO: WIP


### Proxmox Builder

The [Proxmox](infra/proxmox.md) Packer builder is able to create virtual machines and store them as new images using [proxmox-clone](https://developer.hashicorp.com/packer/plugins/builders/proxmox/clone), and [proxmox-iso](https://developer.hashicorp.com/packer/plugins/builders/proxmox/iso).

#### Authentication

TODO: WIP

You can also use the [environment variables](linux/environment-variables-in-linux.md) `PROXMOX_URL`, `PROXMOX_USERNAME`, `PROXMOX_PASSWORD`, and `PROXMOX_TOKEN` to authenticate to [Proxmox](infra/proxmox.md).

#### Template

```hcl

WIP: TODO

```


## Quick Start

**Note:** There is a great
[introduction and getting started guide](https://learn.hashicorp.com/tutorials/packer/get-started-install-cli)
for those with a bit more patience. Otherwise, the quick start below
will get you up and running quickly, at the sacrifice of not explaining some
key points.

First, [download a pre-built Packer
binary](https://www.packer.io/downloads.html) for your operating system or
[compile Packer
yourself](https://github.com/hashicorp/packer/blob/master/.github/CONTRIBUTING.md#setting-up-go-to-work-on-packer).

After Packer is installed, create your first template, which tells Packer
what platforms to build images for and how you want to build them. In our
case, we'll create a simple AMI that has Redis pre-installed.

Save this file as `quick-start.pkr.hcl`. Export your AWS credentials as the
`AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` environment variables.

```hcl
variable "access_key" {
  type    = string
  default = "${env("AWS_ACCESS_KEY_ID")}"
}

variable "secret_key" {
  type      = string
  default   = "${env("AWS_SECRET_ACCESS_KEY")}"
  sensitive = true
}

locals { timestamp = regex_replace(timestamp(), "[- TZ:]", "") }

source "amazon-ebs" "quick-start" {
  access_key    = "${var.access_key}"
  ami_name      = "packer-example ${local.timestamp}"
  instance_type = "t2.micro"
  region        = "us-east-1"
  secret_key    = "${var.secret_key}"
  source_ami    = "ami-af22d9b9"
  ssh_username  = "ubuntu"
}

build {
  sources = ["source.amazon-ebs.quick-start"]
}
```

Next, tell Packer to build the image:

```shell
packer build quick-start.pkr.hcl
...
```

Packer will build an AMI according to the "quick-start" template. The AMI
will be available in your AWS account. To delete the AMI, you must manually
delete it using the [AWS console](https://console.aws.amazon.com/). Packer
builds your images, it does not manage their lifecycle. Where they go, how
they're run, etc., is up to you.

## Documentation

Comprehensive documentation is viewable on the Packer website at https://www.packer.io/docs.
