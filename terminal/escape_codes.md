# Terminal Escape Code Cheatsheet

A list of commonly used escape codes in terminal emulators.

## Table Of Contents

- [Control Escape Codes](#control-escape-codes)
- [8 Color Escape Codes](#8-color-escape-codes)
- [256 Color Escape Codes](#256-color-escape-codes)
- [True Color](#true-color)
- [See Also](#see-also)

## Control Escape Codes

| **Key Name** | **Escape Code** | | **Key Name** | **Escape Code** |
| --- | --- |-| --- | --- |
| S-up | `\x1b[1;2A` | | S-down | `\x1b[1;2B` |
| S-right | `\x1b[1;2C` | | S-left | `\x1b[1;2D` |
| S-end | `\x1b[1;2F` | | S-home | `\x1b[1;2H` |
| M-up | `\x1b[1;3A` | | M-down | `\x1b[1;3B` |
| M-right | `\x1b[1;3C` | | M-left | `\x1b[1;3D` |
| M-end | `\x1b[1;3F` | | M-home | `\x1b[1;3H` |
| M-S-up | `\x1b[1;4A` | | M-S-down | `\x1b[1;4B` |
| M-S-right | `\x1b[1;4C` | | M-S-left | `\x1b[1;4D` |
| M-S-end | `\x1b[1;4F` | | M-S-home | `\x1b[1;4H` |
| C-up | `\x1b[1;5A` | | C-down | `\x1b[1;5B` |
| C-right | `\x1b[1;5C` | | C-left | `\x1b[1;5D` |
| C-end | `\x1b[1;5F` | | C-home | `\x1b[1;5H` |
| C-S-up | `\x1b[1;6A` | | C-S-down | `\x1b[1;6B` |
| C-S-right | `\x1b[1;6C` | | C-S-left | `\x1b[1;6D` |
| C-S-end | `\x1b[1;6F` | | C-S-home | `\x1b[1;6H` |
| C-M-up | `\x1b[1;7A` | | C-M-down | `\x1b[1;7B` |
| C-M-right | `\x1b[1;7C` | | C-M-left | `\x1b[1;7D` |
| C-M-end | `\x1b[1;7F` | | C-M-home | `\x1b[1;7H` |
| C-M-S-up | `\x1b[1;8A` | | C-M-S-down | `\x1b[1;8B` |
| C-M-S-right | `\x1b[1;8C` | | C-M-S-left | `\x1b[1;8D` |
| C-M-S-end | `\x1b[1;8F` | | C-M-S-home | `\x1b[1;8H` |
| M-insert | `\x1b[2;3~` | | M-S-insert | `\x1b[2;4~` |
| C-insert | `\x1b[2;5~` | | C-S-insert | `\x1b[2;6~` |
| C-M-insert | `\x1b[2;7~` | | C-M-S-insert | `\x1b[2;8~` |
| S-delete | `\x1b[3;2~` | | M-delete | `\x1b[3;3~` |
| M-S-delete | `\x1b[3;4~` | | C-delete | `\x1b[3;5~` |
| C-S-delete | `\x1b[3;6~` | | C-M-delete | `\x1b[3;7~` |
| C-M-S-delete | `\x1b[3;8~` | | S-prior | `\x1b[5;2~` |
| M-prior | `\x1b[5;3~` | | M-S-prior | `\x1b[5;4~` |
| C-prior | `\x1b[5;5~` | | C-S-prior | `\x1b[5;6~` |
| C-M-prior | `\x1b[5;7~` | | C-M-S-prior | `\x1b[5;8~` |
| S-next | `\x1b[6;2~` | | M-next | `\x1b[6;3~` |
| M-S-next | `\x1b[6;4~` | | C-next | `\x1b[6;5~` |
| C-S-next | `\x1b[6;6~` | | C-M-next | `\x1b[6;7~` |
| C-M-S-next | `\x1b[6;8~` | | C-backspace | `\x1b[127;5u` |
| C-M-return | `\x1b[13;13u` | | S-return | `\x1b[13;2u` |
| C-return | `\x1b[13;5u` | | C-S-return | `\x1b[13;6u` |
| C-M-tab | `\x1b[9;13u` | | \[S-tab | `\x1b[9;2u` |
| \[C-tab | `\x1b[9;5u` | | \[C-S-tab | `\x1b[9;6u` |
| C-M-S-1 | `\x1b[33;14u` | | C-S-1 | `\x1b[33;6u` |
| C-M-\ | `\x1b[34;14u"` | | C-\ | `\x1b[34;6u"` |
| C-M-S-3 | `\x1b[35;14u` | | C-S-3 | `\x1b[35;6u` |
| C-M-S-4 | `\x1b[36;14u` | | C-S-4 | `\x1b[36;6u` |
| C-M-S-5 | `\x1b[37;14u` | | C-S-5 | `\x1b[37;6u` |
| C-M-S-7 | `\x1b[38;14u` | | C-S-7 | `\x1b[38;6u` |
| C-M-' | `\x1b[39;13u` | | C-' | `\x1b[39;5u` |
| C-M-S-9 | `\x1b[40;14u` | | C-S-9 | `\x1b[40;6u` |
| C-M-S-0 | `\x1b[41;14u` | | C-S-0 | `\x1b[41;6u` |
| C-M-S-8 | `\x1b[42;14u` | | C-S-8 | `\x1b[42;6u` |
| C-M-S-= | `\x1b[43;14u` | | C-S-= | `\x1b[43;6u` |
| C-M-, | `\x1b[44;13u` | | C-, | `\x1b[44;5u` |
| C-M-. | `\x1b[46;13u` | | C-. | `\x1b[46;5u` |
| C-M-/ | `\x1b[47;13u` | | C-/ | `\x1b[47;5u` |
| C-M-0 | `\x1b[48;13u` | | C-0 | `\x1b[48;5u` |
| C-M-1 | `\x1b[49;13u` | | C-1 | `\x1b[49;5u` |
| C-M-2 | `\x1b[50;13u` | | C-2 | `\x1b[50;5u` |
| C-M-3 | `\x1b[51;13u` | | C-3 | `\x1b[51;5u` |
| C-M-4 | `\x1b[52;13u` | | C-4 | `\x1b[52;5u` |
| C-M-5 | `\x1b[53;13u` | | C-5 | `\x1b[53;5u` |
| C-M-6 | `\x1b[54;13u` | | C-6 | `\x1b[54;5u` |
| C-M-7 | `\x1b[55;13u` | | C-7 | `\x1b[55;5u` |
| C-M-8 | `\x1b[56;13u` | | C-8 | `\x1b[56;5u` |
| C-M-9 | `\x1b[57;13u` | | C-9 | `\x1b[57;5u` |
| C-M-: | `\x1b[58;14u` | | C-: | `\x1b[58;6u` |
| C-M-; | `\x1b[59;13u` | | C-; | `\x1b[59;5u` |
| C-M-S-, | `\x1b[60;14u` | | C-S-, | `\x1b[60;6u` |
| C-M-= | `\x1b[61;13u` | | C-= | `\x1b[61;5u` |
| C-M-S-. | `\x1b[62;14u` | | C-S-. | `\x1b[62;6u` |
| C-M-\ | `\x1b[92;13u` | | | |

## 8 Color Escape Codes

| **Name** | **Hex Color Code** | **Foreground Escape Code** | **Background Escape Code** |
| ---- | ----           | ----                   | ----                   |
| Black | `#000000` | `\x1b[1;30m` | `\x1b[1;40m` |
| Red | `#cc0000` | `\x1b[1;31m` | `\x1b[1;41m` |
| Green | `#4e9a06` | `\x1b[1;32m` | `\x1b[1;42m` |
| Yellow | `#c4a000` | `\x1b[1;33m` | `\x1b[1;43m` |
| Blue | `#729fcf` | `\x1b[1;34m` | `\x1b[1;44m` |
| Magenta | `#75507b` | `\x1b[1;35m` | `\x1b[1;45m` |
| Cyan | `#06989a` | `\x1b[1;36m` | `\x1b[1;46m` |
| White | `#d3d7cf` | `\x1b[1;37m` | `\x1b[1;47m` |
| Default | | `\x1b[1;39m` | `\x1b[1;49m` |

## 256 Color Escape Codes

|  | **Name** | **Hex Color Code** | **Foreground Escape Code** | **Background Escape Code** |
| --- | --- | --- | --- | --- |
| 0 | Black (SYSTEM) | `#000000` | `\x1b[38:5:0m` | `\x1b[48:5:0m` |
| 1 | Maroon (SYSTEM) | `#800000` | `\x1b[38:5:1m` | `\x1b[48:5:1m` |
| 2 | Green (SYSTEM) | `#008000` | `\x1b[38:5:2m` | `\x1b[48:5:2m` |
| 3 | Olive (SYSTEM) | `#808000` | `\x1b[38:5:3m` | `\x1b[48:5:3m` |
| 4 | Navy (SYSTEM) | `#000080` | `\x1b[38:5:4m` | `\x1b[48:5:4m` |
| 5 | Purple (SYSTEM) | `#800080` | `\x1b[38:5:5m` | `\x1b[48:5:5m` |
| 6 | Teal (SYSTEM) | `#008080` | `\x1b[38:5:6m` | `\x1b[48:5:6m` |
| 7 | Silver (SYSTEM) | `#c0c0c0` | `\x1b[38:5:7m` | `\x1b[48:5:7m` |
| 8 | Grey (SYSTEM) | `#808080` | `\x1b[38:5:8m` | `\x1b[48:5:8m` |
| 9 | Red (SYSTEM) | `#ff0000` | `\x1b[38:5:9m` | `\x1b[48:5:9m` |
| 10 | Lime (SYSTEM) | `#00ff00` | `\x1b[38:5:10m` | `\x1b[48:5:10m` |
| 11 | Yellow (SYSTEM) | `#ffff00` | `\x1b[38:5:11m` | `\x1b[48:5:11m` |
| 12 | Blue (SYSTEM) | `#0000ff` | `\x1b[38:5:12m` | `\x1b[48:5:12m` |
| 13 | Fuchsia (SYSTEM) | `#ff00ff` | `\x1b[38:5:13m` | `\x1b[48:5:13m` |
| 14 | Aqua (SYSTEM) | `#00ffff` | `\x1b[38:5:14m` | `\x1b[48:5:14m` |
| 15 | White (SYSTEM) | `#ffffff` | `\x1b[38:5:15m` | `\x1b[48:5:15m` |
| 16 | Grey0 | `#000000` | `\x1b[38:5:16m` | `\x1b[48:5:16m` |
| 17 | NavyBlue | `#00005f` | `\x1b[38:5:17m` | `\x1b[48:5:17m` |
| 18 | DarkBlue | `#000087` | `\x1b[38:5:18m` | `\x1b[48:5:18m` |
| 19 | Blue3 | `#0000af` | `\x1b[38:5:19m` | `\x1b[48:5:19m` |
| 20 | Blue3 | `#0000d7` | `\x1b[38:5:20m` | `\x1b[48:5:20m` |
| 21 | Blue1 | `#0000ff` | `\x1b[38:5:21m` | `\x1b[48:5:21m` |
| 22 | DarkGreen | `#005f00` | `\x1b[38:5:22m` | `\x1b[48:5:22m` |
| 23 | DeepSkyBlue4 | `#005f5f` | `\x1b[38:5:23m` | `\x1b[48:5:23m` |
| 24 | DeepSkyBlue4 | `#005f87` | `\x1b[38:5:24m` | `\x1b[48:5:24m` |
| 25 | DeepSkyBlue4 | `#005faf` | `\x1b[38:5:25m` | `\x1b[48:5:25m` |
| 26 | DodgerBlue3 | `#005fd7` | `\x1b[38:5:26m` | `\x1b[48:5:26m` |
| 27 | DodgerBlue2 | `#005fff` | `\x1b[38:5:27m` | `\x1b[48:5:27m` |
| 28 | Green4 | `#008700` | `\x1b[38:5:28m` | `\x1b[48:5:28m` |
| 29 | SpringGreen4 | `#00875f` | `\x1b[38:5:29m` | `\x1b[48:5:29m` |
| 30 | Turquoise4 | `#008787` | `\x1b[38:5:30m` | `\x1b[48:5:30m` |
| 31 | DeepSkyBlue3 | `#0087af` | `\x1b[38:5:31m` | `\x1b[48:5:31m` |
| 32 | DeepSkyBlue3 | `#0087d7` | `\x1b[38:5:32m` | `\x1b[48:5:32m` |
| 33 | DodgerBlue1 | `#0087ff` | `\x1b[38:5:33m` | `\x1b[48:5:33m` |
| 34 | Green3 | `#00af00` | `\x1b[38:5:34m` | `\x1b[48:5:34m` |
| 35 | SpringGreen3 | `#00af5f` | `\x1b[38:5:35m` | `\x1b[48:5:35m` |
| 36 | DarkCyan | `#00af87` | `\x1b[38:5:36m` | `\x1b[48:5:36m` |
| 37 | LightSeaGreen | `#00afaf` | `\x1b[38:5:37m` | `\x1b[48:5:37m` |
| 38 | DeepSkyBlue2 | `#00afd7` | `\x1b[38:5:38m` | `\x1b[48:5:38m` |
| 39 | DeepSkyBlue1 | `#00afff` | `\x1b[38:5:39m` | `\x1b[48:5:39m` |
| 40 | Green3 | `#00d700` | `\x1b[38:5:40m` | `\x1b[48:5:40m` |
| 41 | SpringGreen3 | `#00d75f` | `\x1b[38:5:41m` | `\x1b[48:5:41m` |
| 42 | SpringGreen2 | `#00d787` | `\x1b[38:5:42m` | `\x1b[48:5:42m` |
| 43 | Cyan3 | `#00d7af` | `\x1b[38:5:43m` | `\x1b[48:5:43m` |
| 44 | DarkTurquoise | `#00d7d7` | `\x1b[38:5:44m` | `\x1b[48:5:44m` |
| 45 | Turquoise2 | `#00d7ff` | `\x1b[38:5:45m` | `\x1b[48:5:45m` |
| 46 | Green1 | `#00ff00` | `\x1b[38:5:46m` | `\x1b[48:5:46m` |
| 47 | SpringGreen2 | `#00ff5f` | `\x1b[38:5:47m` | `\x1b[48:5:47m` |
| 48 | SpringGreen1 | `#00ff87` | `\x1b[38:5:48m` | `\x1b[48:5:48m` |
| 49 | MediumSpringGreen | `#00ffaf` | `\x1b[38:5:49m` | `\x1b[48:5:49m` |
| 50 | Cyan2 | `#00ffd7` | `\x1b[38:5:50m` | `\x1b[48:5:50m` |
| 51 | Cyan1 | `#00ffff` | `\x1b[38:5:51m` | `\x1b[48:5:51m` |
| 52 | DarkRed | `#5f0000` | `\x1b[38:5:52m` | `\x1b[48:5:52m` |
| 53 | DeepPink4 | `#5f005f` | `\x1b[38:5:53m` | `\x1b[48:5:53m` |
| 54 | Purple4 | `#5f0087` | `\x1b[38:5:54m` | `\x1b[48:5:54m` |
| 55 | Purple4 | `#5f00af` | `\x1b[38:5:55m` | `\x1b[48:5:55m` |
| 56 | Purple3 | `#5f00d7` | `\x1b[38:5:56m` | `\x1b[48:5:56m` |
| 57 | BlueViolet | `#5f00ff` | `\x1b[38:5:57m` | `\x1b[48:5:57m` |
| 58 | Orange4 | `#5f5f00` | `\x1b[38:5:58m` | `\x1b[48:5:58m` |
| 59 | Grey37 | `#5f5f5f` | `\x1b[38:5:59m` | `\x1b[48:5:59m` |
| 60 | MediumPurple4 | `#5f5f87` | `\x1b[38:5:60m` | `\x1b[48:5:60m` |
| 61 | SlateBlue3 | `#5f5faf` | `\x1b[38:5:61m` | `\x1b[48:5:61m` |
| 62 | SlateBlue3 | `#5f5fd7` | `\x1b[38:5:62m` | `\x1b[48:5:62m` |
| 63 | RoyalBlue1 | `#5f5fff` | `\x1b[38:5:63m` | `\x1b[48:5:63m` |
| 64 | Chartreuse4 | `#5f8700` | `\x1b[38:5:64m` | `\x1b[48:5:64m` |
| 65 | DarkSeaGreen4 | `#5f875f` | `\x1b[38:5:65m` | `\x1b[48:5:65m` |
| 66 | PaleTurquoise4 | `#5f8787` | `\x1b[38:5:66m` | `\x1b[48:5:66m` |
| 67 | SteelBlue | `#5f87af` | `\x1b[38:5:67m` | `\x1b[48:5:67m` |
| 68 | SteelBlue3 | `#5f87d7` | `\x1b[38:5:68m` | `\x1b[48:5:68m` |
| 69 | CornflowerBlue | `#5f87ff` | `\x1b[38:5:69m` | `\x1b[48:5:69m` |
| 70 | Chartreuse3 | `#5faf00` | `\x1b[38:5:70m` | `\x1b[48:5:70m` |
| 71 | DarkSeaGreen4 | `#5faf5f` | `\x1b[38:5:71m` | `\x1b[48:5:71m` |
| 72 | CadetBlue | `#5faf87` | `\x1b[38:5:72m` | `\x1b[48:5:72m` |
| 73 | CadetBlue | `#5fafaf` | `\x1b[38:5:73m` | `\x1b[48:5:73m` |
| 74 | SkyBlue3 | `#5fafd7` | `\x1b[38:5:74m` | `\x1b[48:5:74m` |
| 75 | SteelBlue1 | `#5fafff` | `\x1b[38:5:75m` | `\x1b[48:5:75m` |
| 76 | Chartreuse3 | `#5fd700` | `\x1b[38:5:76m` | `\x1b[48:5:76m` |
| 77 | PaleGreen3 | `#5fd75f` | `\x1b[38:5:77m` | `\x1b[48:5:77m` |
| 78 | SeaGreen3 | `#5fd787` | `\x1b[38:5:78m` | `\x1b[48:5:78m` |
| 79 | Aquamarine3 | `#5fd7af` | `\x1b[38:5:79m` | `\x1b[48:5:79m` |
| 80 | MediumTurquoise | `#5fd7d7` | `\x1b[38:5:80m` | `\x1b[48:5:80m` |
| 81 | SteelBlue1 | `#5fd7ff` | `\x1b[38:5:81m` | `\x1b[48:5:81m` |
| 82 | Chartreuse2 | `#5fff00` | `\x1b[38:5:82m` | `\x1b[48:5:82m` |
| 83 | SeaGreen2 | `#5fff5f` | `\x1b[38:5:83m` | `\x1b[48:5:83m` |
| 84 | SeaGreen1 | `#5fff87` | `\x1b[38:5:84m` | `\x1b[48:5:84m` |
| 85 | SeaGreen1 | `#5fffaf` | `\x1b[38:5:85m` | `\x1b[48:5:85m` |
| 86 | Aquamarine1 | `#5fffd7` | `\x1b[38:5:86m` | `\x1b[48:5:86m` |
| 87 | DarkSlateGray2 | `#5fffff` | `\x1b[38:5:87m` | `\x1b[48:5:87m` |
| 88 | DarkRed | `#870000` | `\x1b[38:5:88m` | `\x1b[48:5:88m` |
| 89 | DeepPink4 | `#87005f` | `\x1b[38:5:89m` | `\x1b[48:5:89m` |
| 90 | DarkMagenta | `#870087` | `\x1b[38:5:90m` | `\x1b[48:5:90m` |
| 91 | DarkMagenta | `#8700af` | `\x1b[38:5:91m` | `\x1b[48:5:91m` |
| 92 | DarkViolet | `#8700d7` | `\x1b[38:5:92m` | `\x1b[48:5:92m` |
| 93 | Purple | `#8700ff` | `\x1b[38:5:93m` | `\x1b[48:5:93m` |
| 94 | Orange4 | `#875f00` | `\x1b[38:5:94m` | `\x1b[48:5:94m` |
| 95 | LightPink4 | `#875f5f` | `\x1b[38:5:95m` | `\x1b[48:5:95m` |
| 96 | Plum4 | `#875f87` | `\x1b[38:5:96m` | `\x1b[48:5:96m` |
| 97 | MediumPurple3 | `#875faf` | `\x1b[38:5:97m` | `\x1b[48:5:97m` |
| 98 | MediumPurple3 | `#875fd7` | `\x1b[38:5:98m` | `\x1b[48:5:98m` |
| 99 | SlateBlue1 | `#875fff` | `\x1b[38:5:99m` | `\x1b[48:5:99m` |
| 100 | Yellow4 | `#878700` | `\x1b[38:5:100m` | `\x1b[48:5:100m` |
| 101 | Wheat4 | `#87875f` | `\x1b[38:5:101m` | `\x1b[48:5:101m` |
| 102 | Grey53 | `#878787` | `\x1b[38:5:102m` | `\x1b[48:5:102m` |
| 103 | LightSlateGrey | `#8787af` | `\x1b[38:5:103m` | `\x1b[48:5:103m` |
| 104 | MediumPurple | `#8787d7` | `\x1b[38:5:104m` | `\x1b[48:5:104m` |
| 105 | LightSlateBlue | `#8787ff` | `\x1b[38:5:105m` | `\x1b[48:5:105m` |
| 106 | Yellow4 | `#87af00` | `\x1b[38:5:106m` | `\x1b[48:5:106m` |
| 107 | DarkOliveGreen3 | `#87af5f` | `\x1b[38:5:107m` | `\x1b[48:5:107m` |
| 108 | DarkSeaGreen | `#87af87` | `\x1b[38:5:108m` | `\x1b[48:5:108m` |
| 109 | LightSkyBlue3 | `#87afaf` | `\x1b[38:5:109m` | `\x1b[48:5:109m` |
| 110 | LightSkyBlue3 | `#87afd7` | `\x1b[38:5:110m` | `\x1b[48:5:110m` |
| 111 | SkyBlue2 | `#87afff` | `\x1b[38:5:111m` | `\x1b[48:5:111m` |
| 112 | Chartreuse2 | `#87d700` | `\x1b[38:5:112m` | `\x1b[48:5:112m` |
| 113 | DarkOliveGreen3 | `#87d75f` | `\x1b[38:5:113m` | `\x1b[48:5:113m` |
| 114 | PaleGreen3 | `#87d787` | `\x1b[38:5:114m` | `\x1b[48:5:114m` |
| 115 | DarkSeaGreen3 | `#87d7af` | `\x1b[38:5:115m` | `\x1b[48:5:115m` |
| 116 | DarkSlateGray3 | `#87d7d7` | `\x1b[38:5:116m` | `\x1b[48:5:116m` |
| 117 | SkyBlue1 | `#87d7ff` | `\x1b[38:5:117m` | `\x1b[48:5:117m` |
| 118 | Chartreuse1 | `#87ff00` | `\x1b[38:5:118m` | `\x1b[48:5:118m` |
| 119 | LightGreen | `#87ff5f` | `\x1b[38:5:119m` | `\x1b[48:5:119m` |
| 120 | LightGreen | `#87ff87` | `\x1b[38:5:120m` | `\x1b[48:5:120m` |
| 121 | PaleGreen1 | `#87ffaf` | `\x1b[38:5:121m` | `\x1b[48:5:121m` |
| 122 | Aquamarine1 | `#87ffd7` | `\x1b[38:5:122m` | `\x1b[48:5:122m` |
| 123 | DarkSlateGray1 | `#87ffff` | `\x1b[38:5:123m` | `\x1b[48:5:123m` |
| 124 | Red3 | `#af0000` | `\x1b[38:5:124m` | `\x1b[48:5:124m` |
| 125 | DeepPink4 | `#af005f` | `\x1b[38:5:125m` | `\x1b[48:5:125m` |
| 126 | MediumVioletRed | `#af0087` | `\x1b[38:5:126m` | `\x1b[48:5:126m` |
| 127 | Magenta3 | `#af00af` | `\x1b[38:5:127m` | `\x1b[48:5:127m` |
| 128 | DarkViolet | `#af00d7` | `\x1b[38:5:128m` | `\x1b[48:5:128m` |
| 129 | Purple | `#af00ff` | `\x1b[38:5:129m` | `\x1b[48:5:129m` |
| 130 | DarkOrange3 | `#af5f00` | `\x1b[38:5:130m` | `\x1b[48:5:130m` |
| 131 | IndianRed | `#af5f5f` | `\x1b[38:5:131m` | `\x1b[48:5:131m` |
| 132 | HotPink3 | `#af5f87` | `\x1b[38:5:132m` | `\x1b[48:5:132m` |
| 133 | MediumOrchid3 | `#af5faf` | `\x1b[38:5:133m` | `\x1b[48:5:133m` |
| 134 | MediumOrchid | `#af5fd7` | `\x1b[38:5:134m` | `\x1b[48:5:134m` |
| 135 | MediumPurple2 | `#af5fff` | `\x1b[38:5:135m` | `\x1b[48:5:135m` |
| 136 | DarkGoldenrod | `#af8700` | `\x1b[38:5:136m` | `\x1b[48:5:136m` |
| 137 | LightSalmon3 | `#af875f` | `\x1b[38:5:137m` | `\x1b[48:5:137m` |
| 138 | RosyBrown | `#af8787` | `\x1b[38:5:138m` | `\x1b[48:5:138m` |
| 139 | Grey63 | `#af87af` | `\x1b[38:5:139m` | `\x1b[48:5:139m` |
| 140 | MediumPurple2 | `#af87d7` | `\x1b[38:5:140m` | `\x1b[48:5:140m` |
| 141 | MediumPurple1 | `#af87ff` | `\x1b[38:5:141m` | `\x1b[48:5:141m` |
| 142 | Gold3 | `#afaf00` | `\x1b[38:5:142m` | `\x1b[48:5:142m` |
| 143 | DarkKhaki | `#afaf5f` | `\x1b[38:5:143m` | `\x1b[48:5:143m` |
| 144 | NavajoWhite3 | `#afaf87` | `\x1b[38:5:144m` | `\x1b[48:5:144m` |
| 145 | Grey69 | `#afafaf` | `\x1b[38:5:145m` | `\x1b[48:5:145m` |
| 146 | LightSteelBlue3 | `#afafd7` | `\x1b[38:5:146m` | `\x1b[48:5:146m` |
| 147 | LightSteelBlue | `#afafff` | `\x1b[38:5:147m` | `\x1b[48:5:147m` |
| 148 | Yellow3 | `#afd700` | `\x1b[38:5:148m` | `\x1b[48:5:148m` |
| 149 | DarkOliveGreen3 | `#afd75f` | `\x1b[38:5:149m` | `\x1b[48:5:149m` |
| 150 | DarkSeaGreen3 | `#afd787` | `\x1b[38:5:150m` | `\x1b[48:5:150m` |
| 151 | DarkSeaGreen2 | `#afd7af` | `\x1b[38:5:151m` | `\x1b[48:5:151m` |
| 152 | LightCyan3 | `#afd7d7` | `\x1b[38:5:152m` | `\x1b[48:5:152m` |
| 153 | LightSkyBlue1 | `#afd7ff` | `\x1b[38:5:153m` | `\x1b[48:5:153m` |
| 154 | GreenYellow | `#afff00` | `\x1b[38:5:154m` | `\x1b[48:5:154m` |
| 155 | DarkOliveGreen2 | `#afff5f` | `\x1b[38:5:155m` | `\x1b[48:5:155m` |
| 156 | PaleGreen1 | `#afff87` | `\x1b[38:5:156m` | `\x1b[48:5:156m` |
| 157 | DarkSeaGreen2 | `#afffaf` | `\x1b[38:5:157m` | `\x1b[48:5:157m` |
| 158 | DarkSeaGreen1 | `#afffd7` | `\x1b[38:5:158m` | `\x1b[48:5:158m` |
| 159 | PaleTurquoise1 | `#afffff` | `\x1b[38:5:159m` | `\x1b[48:5:159m` |
| 160 | Red3 | `#d70000` | `\x1b[38:5:160m` | `\x1b[48:5:160m` |
| 161 | DeepPink3 | `#d7005f` | `\x1b[38:5:161m` | `\x1b[48:5:161m` |
| 162 | DeepPink3 | `#d70087` | `\x1b[38:5:162m` | `\x1b[48:5:162m` |
| 163 | Magenta3 | `#d700af` | `\x1b[38:5:163m` | `\x1b[48:5:163m` |
| 164 | Magenta3 | `#d700d7` | `\x1b[38:5:164m` | `\x1b[48:5:164m` |
| 165 | Magenta2 | `#d700ff` | `\x1b[38:5:165m` | `\x1b[48:5:165m` |
| 166 | DarkOrange3 | `#d75f00` | `\x1b[38:5:166m` | `\x1b[48:5:166m` |
| 167 | IndianRed | `#d75f5f` | `\x1b[38:5:167m` | `\x1b[48:5:167m` |
| 168 | HotPink3 | `#d75f87` | `\x1b[38:5:168m` | `\x1b[48:5:168m` |
| 169 | HotPink2 | `#d75faf` | `\x1b[38:5:169m` | `\x1b[48:5:169m` |
| 170 | Orchid | `#d75fd7` | `\x1b[38:5:170m` | `\x1b[48:5:170m` |
| 171 | MediumOrchid1 | `#d75fff` | `\x1b[38:5:171m` | `\x1b[48:5:171m` |
| 172 | Orange3 | `#d78700` | `\x1b[38:5:172m` | `\x1b[48:5:172m` |
| 173 | LightSalmon3 | `#d7875f` | `\x1b[38:5:173m` | `\x1b[48:5:173m` |
| 174 | LightPink3 | `#d78787` | `\x1b[38:5:174m` | `\x1b[48:5:174m` |
| 175 | Pink3 | `#d787af` | `\x1b[38:5:175m` | `\x1b[48:5:175m` |
| 176 | Plum3 | `#d787d7` | `\x1b[38:5:176m` | `\x1b[48:5:176m` |
| 177 | Violet | `#d787ff` | `\x1b[38:5:177m` | `\x1b[48:5:177m` |
| 178 | Gold3 | `#d7af00` | `\x1b[38:5:178m` | `\x1b[48:5:178m` |
| 179 | LightGoldenrod3 | `#d7af5f` | `\x1b[38:5:179m` | `\x1b[48:5:179m` |
| 180 | Tan | `#d7af87` | `\x1b[38:5:180m` | `\x1b[48:5:180m` |
| 181 | MistyRose3 | `#d7afaf` | `\x1b[38:5:181m` | `\x1b[48:5:181m` |
| 182 | Thistle3 | `#d7afd7` | `\x1b[38:5:182m` | `\x1b[48:5:182m` |
| 183 | Plum2 | `#d7afff` | `\x1b[38:5:183m` | `\x1b[48:5:183m` |
| 184 | Yellow3 | `#d7d700` | `\x1b[38:5:184m` | `\x1b[48:5:184m` |
| 185 | Khaki3 | `#d7d75f` | `\x1b[38:5:185m` | `\x1b[48:5:185m` |
| 186 | LightGoldenrod2 | `#d7d787` | `\x1b[38:5:186m` | `\x1b[48:5:186m` |
| 187 | LightYellow3 | `#d7d7af` | `\x1b[38:5:187m` | `\x1b[48:5:187m` |
| 188 | Grey84 | `#d7d7d7` | `\x1b[38:5:188m` | `\x1b[48:5:188m` |
| 189 | LightSteelBlue1 | `#d7d7ff` | `\x1b[38:5:189m` | `\x1b[48:5:189m` |
| 190 | Yellow2 | `#d7ff00` | `\x1b[38:5:190m` | `\x1b[48:5:190m` |
| 191 | DarkOliveGreen1 | `#d7ff5f` | `\x1b[38:5:191m` | `\x1b[48:5:191m` |
| 192 | DarkOliveGreen1 | `#d7ff87` | `\x1b[38:5:192m` | `\x1b[48:5:192m` |
| 193 | DarkSeaGreen1 | `#d7ffaf` | `\x1b[38:5:193m` | `\x1b[48:5:193m` |
| 194 | Honeydew2 | `#d7ffd7` | `\x1b[38:5:194m` | `\x1b[48:5:194m` |
| 195 | LightCyan1 | `#d7ffff` | `\x1b[38:5:195m` | `\x1b[48:5:195m` |
| 196 | Red1 | `#ff0000` | `\x1b[38:5:196m` | `\x1b[48:5:196m` |
| 197 | DeepPink2 | `#ff005f` | `\x1b[38:5:197m` | `\x1b[48:5:197m` |
| 198 | DeepPink1 | `#ff0087` | `\x1b[38:5:198m` | `\x1b[48:5:198m` |
| 199 | DeepPink1 | `#ff00af` | `\x1b[38:5:199m` | `\x1b[48:5:199m` |
| 200 | Magenta2 | `#ff00d7` | `\x1b[38:5:200m` | `\x1b[48:5:200m` |
| 201 | Magenta1 | `#ff00ff` | `\x1b[38:5:201m` | `\x1b[48:5:201m` |
| 202 | OrangeRed1 | `#ff5f00` | `\x1b[38:5:202m` | `\x1b[48:5:202m` |
| 203 | IndianRed1 | `#ff5f5f` | `\x1b[38:5:203m` | `\x1b[48:5:203m` |
| 204 | IndianRed1 | `#ff5f87` | `\x1b[38:5:204m` | `\x1b[48:5:204m` |
| 205 | HotPink | `#ff5faf` | `\x1b[38:5:205m` | `\x1b[48:5:205m` |
| 206 | HotPink | `#ff5fd7` | `\x1b[38:5:206m` | `\x1b[48:5:206m` |
| 207 | MediumOrchid1 | `#ff5fff` | `\x1b[38:5:207m` | `\x1b[48:5:207m` |
| 208 | DarkOrange | `#ff8700` | `\x1b[38:5:208m` | `\x1b[48:5:208m` |
| 209 | Salmon1 | `#ff875f` | `\x1b[38:5:209m` | `\x1b[48:5:209m` |
| 210 | LightCoral | `#ff8787` | `\x1b[38:5:210m` | `\x1b[48:5:210m` |
| 211 | PaleVioletRed1 | `#ff87af` | `\x1b[38:5:211m` | `\x1b[48:5:211m` |
| 212 | Orchid2 | `#ff87d7` | `\x1b[38:5:212m` | `\x1b[48:5:212m` |
| 213 | Orchid1 | `#ff87ff` | `\x1b[38:5:213m` | `\x1b[48:5:213m` |
| 214 | Orange1 | `#ffaf00` | `\x1b[38:5:214m` | `\x1b[48:5:214m` |
| 215 | SandyBrown | `#ffaf5f` | `\x1b[38:5:215m` | `\x1b[48:5:215m` |
| 216 | LightSalmon1 | `#ffaf87` | `\x1b[38:5:216m` | `\x1b[48:5:216m` |
| 217 | LightPink1 | `#ffafaf` | `\x1b[38:5:217m` | `\x1b[48:5:217m` |
| 218 | Pink1 | `#ffafd7` | `\x1b[38:5:218m` | `\x1b[48:5:218m` |
| 219 | Plum1 | `#ffafff` | `\x1b[38:5:219m` | `\x1b[48:5:219m` |
| 220 | Gold1 | `#ffd700` | `\x1b[38:5:220m` | `\x1b[48:5:220m` |
| 221 | LightGoldenrod2 | `#ffd75f` | `\x1b[38:5:221m` | `\x1b[48:5:221m` |
| 222 | LightGoldenrod2 | `#ffd787` | `\x1b[38:5:222m` | `\x1b[48:5:222m` |
| 223 | NavajoWhite1 | `#ffd7af` | `\x1b[38:5:223m` | `\x1b[48:5:223m` |
| 224 | MistyRose1 | `#ffd7d7` | `\x1b[38:5:224m` | `\x1b[48:5:224m` |
| 225 | Thistle1 | `#ffd7ff` | `\x1b[38:5:225m` | `\x1b[48:5:225m` |
| 226 | Yellow1 | `#ffff00` | `\x1b[38:5:226m` | `\x1b[48:5:226m` |
| 227 | LightGoldenrod1 | `#ffff5f` | `\x1b[38:5:227m` | `\x1b[48:5:227m` |
| 228 | Khaki1 | `#ffff87` | `\x1b[38:5:228m` | `\x1b[48:5:228m` |
| 229 | Wheat1 | `#ffffaf` | `\x1b[38:5:229m` | `\x1b[48:5:229m` |
| 230 | Cornsilk1 | `#ffffd7` | `\x1b[38:5:230m` | `\x1b[48:5:230m` |
| 231 | Grey100 | `#ffffff` | `\x1b[38:5:231m` | `\x1b[48:5:231m` |
| 232 | Grey3 | `#080808` | `\x1b[38:5:232m` | `\x1b[48:5:232m` |
| 233 | Grey7 | `#121212` | `\x1b[38:5:233m` | `\x1b[48:5:233m` |
| 234 | Grey11 | `#1c1c1c` | `\x1b[38:5:234m` | `\x1b[48:5:234m` |
| 235 | Grey15 | `#262626` | `\x1b[38:5:235m` | `\x1b[48:5:235m` |
| 236 | Grey19 | `#303030` | `\x1b[38:5:236m` | `\x1b[48:5:236m` |
| 237 | Grey23 | `#3a3a3a` | `\x1b[38:5:237m` | `\x1b[48:5:237m` |
| 238 | Grey27 | `#444444` | `\x1b[38:5:238m` | `\x1b[48:5:238m` |
| 239 | Grey30 | `#4e4e4e` | `\x1b[38:5:239m` | `\x1b[48:5:239m` |
| 240 | Grey35 | `#585858` | `\x1b[38:5:240m` | `\x1b[48:5:240m` |
| 241 | Grey39 | `#626262` | `\x1b[38:5:241m` | `\x1b[48:5:241m` |
| 242 | Grey42 | `#6c6c6c` | `\x1b[38:5:242m` | `\x1b[48:5:242m` |
| 243 | Grey46 | `#767676` | `\x1b[38:5:243m` | `\x1b[48:5:243m` |
| 244 | Grey50 | `#808080` | `\x1b[38:5:244m` | `\x1b[48:5:244m` |
| 245 | Grey54 | `#8a8a8a` | `\x1b[38:5:245m` | `\x1b[48:5:245m` |
| 246 | Grey58 | `#949494` | `\x1b[38:5:246m` | `\x1b[48:5:246m` |
| 247 | Grey62 | `#9e9e9e` | `\x1b[38:5:247m` | `\x1b[48:5:247m` |
| 248 | Grey66 | `#a8a8a8` | `\x1b[38:5:248m` | `\x1b[48:5:248m` |
| 249 | Grey70 | `#b2b2b2` | `\x1b[38:5:249m` | `\x1b[48:5:249m` |
| 250 | Grey74 | `#bcbcbc` | `\x1b[38:5:250m` | `\x1b[48:5:250m` |
| 251 | Grey78 | `#c6c6c6` | `\x1b[38:5:251m` | `\x1b[48:5:251m` |
| 252 | Grey82 | `#d0d0d0` | `\x1b[38:5:252m` | `\x1b[48:5:252m` |
| 253 | Grey85 | `#dadada` | `\x1b[38:5:253m` | `\x1b[48:5:253m` |
| 254 | Grey89 | `#e4e4e4` | `\x1b[38:5:254m` | `\x1b[48:5:254m` |
| 255 | Grey93 | `#eeeeee` | `\x1b[38:5:255m` | `\x1b[48:5:255m` |

## True Color

|  | Escape Code | Example |
| --- | --- | --- |
| foreground color | `\x1b[38;2;${red};${green};${blue}m` | `\x1b[38;2;255;0;0m` |
| background color | `\x1b[48;2;${red};${green};${blue}m` | `\x1b[48;2;255;0;0m` |

## See also

- [Screen](screen.md)
- [Tmux](tmux.md)
- [iTerm2](iterm2.md)
- [Shortcuts](../keyboard/shortcuts.md)
- [xmodmap](../keyboard/xmodmap.md)
- [xvkbd](../keyboard/xvkbd.md)
- [xbindkeys](../keyboard/xbindkeys.md)
- [Kitty](kitty/kitty.md)
