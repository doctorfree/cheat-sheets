---
tags:
  - projects
  - kasm
  - workspace
categories:
  - kasm
  - linux
---

## Deluxe Desktop Kasm Workspace

The `Deluxe Desktop` Kasm workspace is designed to integrate many of the features of other Record Technologies Kasm workspaces into a customized Ubuntu 22.04 desktop environment. The `Deluxe Desktop` Kasm workspace image includes:

* [Asciiville](https://github.com/doctorfree/Asciiville#readme): Ascii art, utilities, games, more
* [Ascii Games](https://github.com/doctorfree/asciigames#readme): Collection of Ascii games
* `CloudStorage`: Utilizes [rclone](https://github.com/rclone/rclone), a command-line program to manage files on cloud storage
* [Neovim](https://github.com/doctorfree/nvim-lazyman#readme): Neovim, neovide, lazyman, much more
* [Open-Source Intelligence](https://en.wikipedia.org/wiki/Open-source_intelligence): Reconnaissance tool, forensics, link analyzer, ...
* [Spiderfoot](https://github.com/smicallef/spiderfoot): A reconnaissance tool that automatically queries public data sources to gather intelligence
* [Wing cloud programming language](https://www.winglang.io): Wing programming language, examples, and editors

## Kasm workspace persistent profile

The `Deluxe Desktop` Kasm workspace should be deployed with a persistent profile. This preserves the home directory of the `kasm-user` user. For example, use the following persistent profile configured in the `Deluxe Desktop` workspace:

```json
/u/kasm_profiles/{image_id}/{user_id}
```

Where `/u/kasm_profiles/` has been created on the Kasm server host.

Using a persistent profile in a Kasm workspace preserves any changes the the Kasm user's home directory across sessions allowing for personalized customization and configuration.

## Help documents

Record Technologies Kasm workspaces include a help facility that integrates the `ranger` file manager, the `glow` markdown previewer, and the `Obsidian` notes application. Help documents are provided in an Obsidian vault and can be browsed either directly with Obsidian or via the `ranger` file manager. Selecting a help document in `ranger` and pressing `<Enter>` will open Obsidian with the selected document.

Help pages for `rclone`, `spiderfoot`, `zsh`, `neovim`, and many others may serve as a guide to getting started with the Deluxe Desktop workspace.
