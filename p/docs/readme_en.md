

more docs on feature,manual of onekeydevdesk：
=====
 
[inst.sh](../instintro/) is a script which installs onekeydevdesk (and other os) to various targets and help maintain it as onekeydevdesk os's recovery, like web assistant for synology's dsm  

[ci.sh](../ciintro/) is a ci/cd builder script,which can construct up all "your own [ddhub](p/ciusage/)" (including inst.sh),ci.sh is also referred to as onekeydevdesk's codebase,which was made up of ci.sh, and other well-arranged asserts and src, they formed all the onekeydevdesk's codebase  

+  inst.sh
     +  [inst介绍：什么是inst.sh及它与onekeydevdesk ci.sh的关系](../instintro/)
     +  [inst使用：利用inst.sh安装onekeydevdesk，安装自定义镜像，及简单制造打包镜像](../instusage/)
     +  [todo高级：利用inst.sh安装云黑群/云黑果镜像]
     +  [todo高级：对接inst.sh使用gitee,github建立你自己的镜像托管源，组装一体仓库]
     +  [todo高级：扩展inst.sh，手动加入驱动]
     +  [todo高级：扩展inst.sh，加入复杂机型网络及非DHCP支持的机型支持]
     +  [todo高级：把进度显示附加到你现在使用的其它一键DD版本]
+  onekeydevdesk
     +  [什么是onekeydevdesk os](../1kddintro/)
     +  [设置onekeydevdesk](../1kddusage/)
     +  [设置和使用deepin](../dpiusage/)
     +  [设置和使用cloudrevebox](../cloudreveboxusage/)
     +  [todo高级：使用openwrt容器打造云软路由]
     +  [todo高级：使用osx打造本地mac的mateos]
     +  [todo高级：利用onekeydevdesk中的pve封装制造硬盘镜像]
     +  [直接把pve面板当web面板]
     +  [todo高级：利用onekeydevdesk汇聚闲置机打造你的个人IDC]
+  onekeydevdesk custom
     +  [oracle](../oracle/)
     +  [ksle](../ksle/)
     +  [spartan](../spartan/)
+  onekeydevdesk ci.sh
     +  [onekeydevdesk ci介绍](../ciintro/)
     +  [onekeydevdesk ci使用：跑github actions编译inst.sh和onekeydevdesk](../ciusage/)
