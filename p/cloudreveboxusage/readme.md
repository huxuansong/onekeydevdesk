

设置cloudrevebox lxc
=============

下载镜像
------

lxc template lxccloudrevebox

以下x指一个数字：

创建时使用10.10.10.x/24这样的手动地址101010x这样的ID命名，网关是10.10.10.10


编辑nano /etc/network/interfaces
------

nano /etc/network/interfaces，加入如下：

${initalno: -1}是你的10.10.10.4，这里${initalno: -1}就是4

```
post-up   iptables -t nat -A PREROUTING -p tcp --dport 80${initalno: -1}0:80${initalno: -1}9 -j DNAT --to 10.10.10.${initalno: -1}:80${initalno: -1}0-80${initalno: -1}9/80${initalno: -1}0
post-up   iptables -A INPUT -p tcp --dport 80${initalno: -1}0:80${initalno: -1}9 -j ACCEPT
```

/etc/init.d/networking restart

编辑配置文件
------

nano /opt/tomcat/conf/server.xml，把8011，改成80x1,x是你的${initalno: -1}

nano /opt/cloudreve/conf.ini也一样

reboot

使用：
-----

访问http://ip:80x0,80x1



