

什么是onekeydevdesk
=============


概述
------

onekeydevdesk lxc：

> 实现特点：全部使用开源搭建不使用闭源成份，定制和增强pve，使用lxc加安全策略实现全linux family的多云桌面方案，无须CPU支持虚拟化，不使用docker这种反使用习惯的只读容器。  
> 目前集成包含pc linux和andriod,wine在内的二个lxc container os，一个lxc deepin桌面 container os，beaker集成pveman客户端。  
> 零配置，开箱即用，采用live机制，整个系统处在readonly文件中，数据区启动时mount进来隔离在文件夹内，与系统区互不污染。    
> 可用于开发也可用于写作同步等生产。可用于云主机虚拟机本机装机（虚拟机目前只适配了pd16，本机适配了mbp12,1）  
> 强调DEVOPS即桌面即浏览器的沉浸环境(主系统as虚拟机管理器,devops as desk)，和日常使用即轻运维/编程的碎片化应用方式。

onekeydevdesk qemu：

> 实现特点：除集成的客户OS外，全部使用开源搭建，定制和增强pve，使用单显卡直通实现一机多OS并行运行和切换,避免了虚拟化显卡的和vdi全虚拟化的需要。需要CPU支持硬件虚拟化。  
> 目前集成win,osx,dsm。  
> 其它同lxc。  



