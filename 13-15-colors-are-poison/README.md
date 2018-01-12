
## .Xresources syntax

include file (OBSquotes are important):
`#include "PATH_RELATIVE_TO_XRESOURCES"`

define variable:
`#define  VARIABLE VALUE`

custom resource:
`name.class.resource: value/variable`

-------------------------------

## on startup

load .Xresources in `~/.xinitrc` (recommended):
`[[ -f ~/.Xresources ]] && xrdb -merge -I$HOME ~/.Xresources`

load .Xresources in `~/.config/i3/config`:
`set $HOME ABSOLUTE_PATH_TO_HOMEFOLDER` (/home/bud)
`exec --no-startup-id xrdb -merge -I$HOME ~/.Xresources`
`exec --no-startup-id exec i3-msg -q restart`  

*If you have to load from i3 it's best to use `reloader` script instead.*

-------------------------------

## reloader

``` shell
#!/bin/bash

xrdb -merge -I$HOME ~/.Xresources
i3-msg restart
polybar-msg cmd restart
```

------------------------------

## useful commands

merge new changes:
`xrdb -merge ~/.Xresources`

replace .Xresources
`xrdb -load ~/.Xresources`

list current settings in .Xresources:
`xrdb -query`

list installed fonts:
`fc-list | grep FONTNAME`

instant font test:
`printf '\e]710;%s\007' "xft:FONT"`


:antialias=false <- try using this font setting

-------------------------------

## get resources

use resource in i3:
`set_from_resource $VARIABLE  XRESOURCE  DEFAULT_VALUE`

use xresource in polybar:
`VARNAME = ${xrdb:XRESOURCE:DEFAULT}`

get xresource from script
`VAR=$(xrdb -query | awk '$1 ~ XRESOURCE":" {print $2}')`

-----------------------------------

## useful links

https://wiki.archlinux.org/index.php/X_resources

https://github.com/jaagr/polybar/wiki/Configuration

https://i3wm.org/docs/userguide.html#xresources

https://www.reddit.com/r/unixporn/wiki/organizing_xresources

Gruvbox color theme by **morhertz** (Pavel Pertsev)
https://github.com/morhetz/gruvbox

Solarized color theme by Ethan Schoonover
http://ethanschoonover.com/solarized

https://github.com/solarized/xresources/blob/master/Xresources.dark



