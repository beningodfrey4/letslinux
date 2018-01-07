polybar doc:
Inter-process-messaging
Module:-ipc

github.com/jaagr/polybar

[module/titlescript]
type = custom/script
tail = true
label = %output%
interval = 3000
exec = SCRIPT_PATH

enable-ipc = true

[module/titlehook]
type = custom/ipc
hook-0 = echo hook1
hook-1 = echo hook2
hook-2 = echo hook3
initial = 1
click-left = polybar-msg hook titlehook 2

polybar-msg hook HOOKNAME HOOKNUMBER


