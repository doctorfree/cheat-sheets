---
tags:
  - projects
  - kasm
  - workspace
categories:
  - kasm
  - linux
---

# Kasm Workspaces

[Kasm Workspaces](https://kasmweb.com) provides enterprise-class orchestration, data loss prevention, and web streaming technology to enable the delivery of containerized workloads to your browser and desktops to end-users.

## Table of Contents

- [Installation](#installation)
  - [Download and extract](#download-and-extract)
  - [To run Kasm on port 8443 with a reverse proxy on 443](#to-run-kasm-on-port-8443-with-a-reverse-proxy-on-443)
- [Custom Docker Images](#custom-docker-images)
- [Cron periodic cleanup and certificate renewal](cron/README.md)
- [References](#references)

## Installation

### Download and extract

```bash
[ -d $HOME/Kasm ] || mkdir -p $HOME/Kasm
cd $HOME/Kasm
curl -O https://kasm-static-content.s3.amazonaws.com/kasm_release_1.14.0.3a7abb.tar.gz
tar -xf kasm_release_1.14.0.3a7abb.tar.gz
sudo bash kasm_release/install.sh --accept-eula --swap-size 8192
```

### To run Kasm on port 8443 with a reverse proxy on 443

```bash
sudo bash kasm_release/install.sh -L 8443 --accept-eula --swap-size 8192
```

- Log into the Web Application at https://<WEBAPP_SERVER>
- Default usernames are `admin@kasm.local` and `user@kasm.local`
- Passwords will be randomly generated and presented at the end of the install
  - Unless the `--admin-password` and/or `--user-password` are specified

## Custom Docker Images

See the Kasm Workspaces documentation on [Building Custom Images](https://kasmweb.com/docs/latest/how_to/building_images.html#).

Many example custom Kasm image builder Dockerfiles can be found at https://github.com/doctorfree/workspaces-images including a `Neovim` image. To build the `Neovim` Workspace image:

```bash
# On the Kasm Workspaces server
git clone https://github.com/doctorfree/workspaces-images
cd workspaces-images
export GH_TOKEN="<YOUR-GITHUB-API-TOKEN>"
./build-neovim
```

After building a custom image, as an administrator in Kasm Workspaces, add the custom Workspace with `Workspaces -> Workspaces -> Add Workspace`. Add the `Neovim` image as:

- **Workspace Type**: `Container`
- **Thumbnail URL**: `https://lazyman.dev/assets/neovim-hicontrast.png`
- **Docker Image**: `<your-dockerhub-user>/<your-dockerhub-repo>:neovim`
- **Cores**: `2`
- **Memory**: `5636`
- **GPU Count**: `0`
- **CPU Allocation Method**: `inherit`
- **Persistent Profile Path**: `/u/kasm_profiles/{image_id}/{user_id}`
- **Docker Run Config Override**: `{ "hostname": "kasm" }`

After adding a Workspace, check `Workspaces -> Registry -> Installed Workspaces` to verify the Workspace is installed. The first time this Workspace session runs the [Lazyman Neovim Configuration Manager](https://github.com/doctorfree/nvim-lazyman) is installed and configured.

## References

- [Kasm Documentation](https://www.kasmweb.com/docs/latest/index.html)
- [Kasm Administration](https://www.kasmweb.com/docs/latest/admin_guide.html)
- [Kasm User Guide](https://www.kasmweb.com/docs/latest/user_guide.html)
- [Kasm Workspaces - Resource Allocation](https://youtu.be/lv85XZ8EdjY?si=xcSfB-EWtu-2tIHQ) (YouTube)
- [KasmVNC](https://www.kasmweb.com/kasmvnc)
- [Record Technologies Kasm Registry](https://doctorfree.github.io/kasm-registry/)
  - [Github Repository](https://github.com/doctorfree/kasm-registry) (deployment details)
- [LinuxServer.io](https://www.linuxserver.io)
  - [3rd Party Workspace Registry](https://kasmregistry.linuxserver.io)
  - [Generate Add Workspace JSON](https://kasmregistry.linuxserver.io/1.0/new)
- [Dockerizing a node.js Web Application](https://semaphoreci.com/community/tutorials/dockerizing-a-node-js-web-application)
