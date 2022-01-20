

设置deepin lxc
=============

下载镜像
------

lxc template lxcdeepin

以下x指一个数字：

创建时使用10.10.10.x/24这样的手动地址101010x这样的ID命名，网关是10.10.10.10

编辑/etc/pve/lxc/xxx.conf
------

nano /etc/pve/lxc/xxx.conf，加入如下：


```
# deny all
lxc.cgroup.devices.deny: a

# basics: null,zero,full,random,urandom tty,consoles,ptmx,pty rtc
lxc.cgroup.devices.allow: c 1:3 rwm
lxc.cgroup.devices.allow: c 1:5 rwm
lxc.cgroup.devices.allow: c 1:7 rwm
lxc.cgroup.devices.allow: c 1:8 rwm
lxc.cgroup.devices.allow: c 1:9 rwm
lxc.cgroup.devices.allow: c 5:0 rwm
lxc.cgroup.devices.allow: c 5:1 rwm
lxc.cgroup.devices.allow: c 5:2 rwm
lxc.cgroup.devices.allow: c 136:* rwm
lxc.cgroup.devices.allow: c 254:0 rm

# for x11
lxc.cgroup.devices.allow: c 226:0 rwm
lxc.cgroup.devices.allow: c 226:128 rwm
lxc.cgroup.devices.allow: c 4:* rwm
lxc.cgroup.devices.allow: c 29:0 rwm
lxc.mount.entry: /dev/dri/card0 dev/dri/card0 none bind,optional,create=file 0 0
lxc.mount.entry: /dev/dri/renderD128 dev/dri/renderD128 none bind,optional,create=file 0 0
lxc.mount.entry: /dev/tty2 dev/tty2 none bind,optional,create=file 0 0
lxc.mount.entry: /dev/tty3 dev/tty3 none bind,optional,create=file 0 0
lxc.mount.entry: /dev/tty4 dev/tty4 none bind,optional,create=file 0 0
lxc.mount.entry: /dev/tty5 dev/tty5 none bind,optional,create=file 0 0
lxc.mount.entry: /dev/tty6 dev/tty6 none bind,optional,create=file 0 0
lxc.mount.entry: /dev/tty7 dev/tty7 none bind,optional,create=file 0 0
lxc.mount.entry: /dev/fb0 dev/fb0 none bind,optional,create=file 0 0
```

编辑/etc/network/interfaces
------

nano /etc/network/interfaces，加入如下：

${initalno: -1}是你的10.10.10.4，这里${initalno: -1}就是4

```
#www,vnc:www cantbe host80,or it will block guest income
post-up   iptables -t nat -A PREROUTING -p tcp --dport 80${initalno: -1}0:80${initalno: -1}9 -j DNAT --to 10.10.10.${initalno: -1}:80${initalno: -1}0-80${initalno: -1}9/80${initalno: -1}0
post-up   iptables -A INPUT -p tcp --dport 80${initalno: -1}0:80${initalno: -1}9 -j ACCEPT
post-up   iptables -t nat -A PREROUTING -p tcp --dport 8059 -j DNAT --to 10.10.10.${initalno: -1}:5900
post-up   iptables -A INPUT -p tcp --dport 8059 -j ACCEPT
```

