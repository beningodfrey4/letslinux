polybar doc:
Inter-process-messaging
Module:-ipc

github.com/jaagr/polybar


$ install -Dm644 /usr/share/doc/polybar/config $HOME/.config/polybar/config
$ polybar example

; this combo is important to overlay tabs.
override-redirect = true
; wm-restack = i3


#!/usr/bin/env sh

# Terminate already running bar instances
killall -q polybar

# Wait until the processes have been shut down
while pgrep -u $UID -x polybar >/dev/null; do sleep 1; done

# Launch bar1 and bar2
polybar example &

---

chmod +x $HOME/.config/polybar/launch.sh

---

exec_always --no-startup-id $HOME/.config/polybar/launch.sh

---

enable-ipc = true

[module/i3title]
type = custom/ipc
hook-0 = i3title
hook-1 = i3title -r
hook-2 = whoami
initial = 1
click-left = polybar-msg -p %pid% hook i3title 2

polybar-msg hook HOOKNAME HOOKNUMBER

---

i3ipc-python-git
/usr/lib/python3.6/site-packages/i3ipc/i3ipc.py

---


