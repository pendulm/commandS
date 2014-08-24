# propcs-ng 3.3.9-3

```
[mike@peijun Documents]$ pacman -Ql procps-ng|grep /bin
procps-ng /usr/bin/
procps-ng /usr/bin/free
procps-ng /usr/bin/pgrep
procps-ng /usr/bin/pidof
procps-ng /usr/bin/pkill
procps-ng /usr/bin/pmap
procps-ng /usr/bin/ps
procps-ng /usr/bin/pwdx
procps-ng /usr/bin/slabtop
procps-ng /usr/bin/sysctl
procps-ng /usr/bin/tload
procps-ng /usr/bin/top
procps-ng /usr/bin/uptime
procps-ng /usr/bin/vmstat
procps-ng /usr/bin/w
procps-ng /usr/bin/watch
```

## ps

### process selection

default: unix PERSONALITY

#### Unix PERSONALITY
`ps -e` or ps -A: all process
`ps -a`: all except session leaders and no tty(normally session leader is a shell, compare with `ps a`)
`ps -d`: all except session leaders
`ps -N`: need some example
`ps -123` and `ps -p 123` and `ps --pid 123`: show process 123
`ps -C java`: show all java process
`ps -C java,bash`
`ps -G mike,501` and `ps --Group`: select real Group ID
`ps -U mike` and `ps --User mike`: select by real User ID
`ps -g admin` and `ps --group 100,admin`: select by effective group id
`ps -u root` and `ps --user root`: select by effective user id
`ps -g 100,101`: select by session id(dont use this)
`ps --ppid 1`: select children of pid 1
`ps -s 500` and `ps --sid 500`: select by session id
`ps -t` or `ps --tty`: select by tty



#### BSD PERSONALITY

`ps a`: all process with a terminal(owned by me)
`ps x`: all process owned by me
`ps ax`: realy all
`ps r`: running process(restrict)
`ps axr`
`ps xr`
`ps T` and `ps t`: all process associated with this terminal(additive)
`ps t pts/1`: select by tty
`ps 123` and `ps -p 123`: show process 123
`ps U admin`: select by effective user id


### output formats



## free

units
-b -k -m -g -t -h

times
-c(count) -s(seconds)

-t mem + swap

used = buffers + cached + process occupied
http://www.quora.com/Linux-Kernel/What-is-the-major-difference-between-the-buffer-cache-and-the-page-cache
http://www.quora.com/What-is-the-difference-between-Buffers-and-Cached-columns-in-proc-meminfo-output

### Question
what/proc/meminfo means?

## top
