# 26 - workspace magic

event.old.num != -1
call('SCRIPT'.split(' ')+[format(event.current.num)])

getpid script
create hookmodule
add workspace to listener script
# {'change': 'init',
# {'change': 'focus',
# {'change': 'empty'


``` shell
# Terminate already running instances of listener
listnpid=$(ps -ef | awk '$NF~"i3listen.py"{print $2}')
[[ -n $listnpid ]] && kill "$listnpid"

# start listener
i3listen.py > /dev/null 2>&1 &
```
