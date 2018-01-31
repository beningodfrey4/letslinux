# Let's linux #019: Fonts Are Awesome

the script and list used to display icons in rofi:
[rofi-fontawesome](https://github.com/wstam88/rofi-fontawesome)  

xclip is needed to put icons in the clipboard.  
[xclip](https://github.com/astrand/xclip)  

[Font Awesome](http://fontawesome.io/)  
[rofi](https://github.com/DaveDavenport/rofi/)  
[polybar](https://github.com/jaagr/polybar)  

add this list to the polybar config:

``` text 
font-1 = FontAwesome5Free:style=Solid:pixelsize=10:antialias=false;3
font-2 = FontAwesome5Brands:style=Solid:pixelsize=10:antialias=false;3
```









get rofi from your package manager or from github

https://github.com/DaveDavenport/rofi/

rofi search for themes in these directories:  
`/usr/share/rofi/themes/`  
`~/.config/rofi`


I take a look at rofis new theme engine. Rofi has a separate `man` page for the themes: `man rofi-theme`
The preinstalled themes are located at this
location:   
`/usr/share/rofi/themes/`  

It also searched for themes in the local directory with this path:  
`~/.config/rofi`  

To change ownership of a file use the `chown` command:  
`chown NEWOWNER FILE(s)`

To list all defined resources in `~/.Xresources` use this command:  
`xrdb -query`

To *fetch* a value from a specific xresource use this command (replace XRESOURCE with the name of a resource)
`VAR=$(xrdb -query | awk '$1 ~ "XRESOURCE:" {print $2}')`  
*This will store the result in the variable Var*  

To replace line matching a SEARCH-criteria within a file, use the `sed` command below. (Replace FILE with the path to a file to search in, replace SEARCH with a regular expression, replace REPLACE with the text you want to replace line(s) matching)
`sed -i --follow-symlinks "/SEARCH/c\REPLACE" "FILE"`





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



