# xmodmap tutorial

Cheat sheet on X11's xmodmap tool.

## What can xmodmap do?

xmodmap is only for remapping keys, for apps running under X11. That's it.

- xmodmap cannot set a key to type key combinations such as Ctrl+c
- xmodmap cannot set a key to run a script.
- xmodmap cannot change key based on which is current app.

## xmodmap example

Here's a quick example: Temporarily swap `Return` and `End` keys

Creat a file at `~/.Xmodmap` with this content:

```text
! swap keys {return, end}

! keycode  36 = Return NoSymbol Return
! keycode 115 = End NoSymbol End

keycode  36 = End NoSymbol End
keycode 115 = Return NoSymbol Return
```

Then run:

```shell
xmodmap ~/.Xmodmap
```

## xmodmap command

```shell
# show current keycode / keysym mapping.
xmodmap -pke
```

```shell
# save current mapping to file
xmodmap -pke > ~/xmodmap_original
```
```shell
# To revert to default keymap, just type:
xmodmap ~/xmodmap_original
```

## Xmodmap Syntax Meaning

Here's part of `xmodmap -pke` output:

```text
keycode  57 = n N n N
keycode  58 = m M m M
keycode  59 = comma less comma less
keycode  60 = period greater period greater
keycode  61 = slash question slash question
keycode  62 = Shift_R NoSymbol Shift_R
keycode  63 = KP_Multiply KP_Multiply KP_Multiply KP_Multiply KP_Multiply KP_Multiply XF86ClearGrab
keycode  64 = Alt_L Meta_L Alt_L Meta_L
keycode  65 = space NoSymbol space
keycode  66 = Caps_Lock NoSymbol Caps_Lock
keycode  67 = F1 F1 F1 F1 F1 F1 XF86Switch_VT_1
keycode  68 = F2 F2 F2 F2 F2 F2 XF86Switch_VT_2
```

The left side is keycode, the right side is its meaning in keysym. The first keysym is the key pressed by itself, the others are with different modifier keys. The meanings are:

* `key` by itself
* `Shift`+`key`
* `mode_switch`+`key`
* `mode_switch`+`Shift`+`key`
* `AltGraph`+`key`
* `AltGraph`+`Shift`+`key`

Each line of `xmodmap -pke` output is a expression that can be read by xmodmap.

For example, type `xmodmap -e "keycode  67 = F2"` to make F1 key send F2. The `-e` option means read in expression.

To revert, just `xmodmap ~/xmodmap_original`.

To create your own map, just create a file with xmodmap expressions, then have xmodmap read it `xmodmap filename`.

## Load Your Keymap When X11 Starts

Name your xmodmap config file as `~/.Xmodmap`. It'll automatically load if you are using Ubuntu.

or, create a file at `~/.xinitrc`, with this content:

```shell
if [ -s ~/.Xmodmap ]; then
    xmodmap ~/.Xmodmap
fi
```

## How to Set Keys for Console?

Xmodmap only works in X11. It does not change keys in Virtual Console or Linux Console (the command line screen when boot up)

## See also

- [xbindkeys](xbindkeys.md)
- [xvkbd](xvkbd.md)
- [iTerm2](iterm2.md)
- [Screen](screen.md)
- [Shortcuts](shortcuts.md)
- [Tmux](tmux.md)
- [Kitty](kitty/kitty.md)
