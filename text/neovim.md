# Neovim

Neovim is a fork of [Vim](vim.md) that strives to improve the extensibility and maintainability of Vim. Some features of the fork include built-in Language Server Protocol support, support for asynchronous I/O, and support for scripting using Lua.

Neovim has the same configuration syntax as Vim (unless vim9script is used); thus the same configuration file can be used with both editors, although there are minor differences in details of options. If the added features of Neovim are not used, Neovim is compatible with almost all of Vim's features.

The Neovim project was started in 2014, with some Vim community members offering early support of the high-level refactoring effort to provide better scripting, plugins, and integration with modern GUIs. The project is free software and its source code is available on GitHub.

Neovim had a successful fundraising in March 2014, supporting at least one full-time developer. Several frontends are under development, making use of Neovim's capabilities.

The Neovim editor is available in an Ubuntu Personal Package Archive, hosted by Canonical and some more conventional package managers, making it possible to install it on a variety of operating systems.

On October 27, 2021, GitHub released a GitHub Copilot (a cloud-based artificial intelligence tool for autocompleting code) plugin for Neovim as a public repository.

Repository: https://github.com/neovim/neovim

Website: https://neovim.io/

![](assets/neovim.png)

## Neovim cheat sheet

Most, if not all, of the information in the [Vim cheat sheet](vim.md)
applies equally to `nvim`.

See https://github.com/sudormrfbin/cheatsheet.nvim for a Neovim plugin
that provides searchable cheatsheets from within Neovim itself.

Neovim, a programmer's text editor based on Vim, provides several modes
for different kinds of text manipulation.

Pressing 'i' in normal mode enters insert mode.
'<Esc>' goes back to normal mode, which doesn't allow regular text insertion.

### Open a file
```shell
nvim path/to/file
```

### Enter text editing mode (insert mode):
```shell
<Esc>i
```

### Copy ("yank") or cut ("delete") the current line (paste it with `P`):
```shell
<Esc>yy|dd
```

### Enter normal mode and undo the last operation:
```shell
<Esc>u
```

### Search for a pattern in the file (press `n`/`N` to go to next/previous match):
```shell
<Esc>/search_pattern<Enter>
```

### Perform a regular expression substitution in the whole file:
```shell
<Esc>:%s/regular_expression/replacement/g<Enter>
```

### Enter normal mode and save (write) the file, and quit:
```shell
<Esc>:wq<Enter>
```

### Quit without saving:
```shell
<Esc>:q!<Enter>
```

## See also

- [Vim](vim.md)
- [Vim/Neovim plugin urls](Plugin-urls.md)
