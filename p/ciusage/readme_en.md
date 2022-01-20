
onekeydevdesk ci.sh manual(how to use onekeydevdesk ci.sh)：
======

onekeydevdesk/onekeydevdesk ci.sh,inst.sh all use free public git services as their storage bases(sometimes git platform has some limits compared non-src storage shedmas,such as gitee has "1m wget limition" ),they can accomplish git with following jobs:

1,ci/cd building
note: github free ci/cd service for privates are very convint,speedy and yet free
2,hosting building target (on another repo,also a repo)
note: sometimes git repo cant be used as cdn



当然，你也可以在本地跑ci.sh编译，这往往是本地调试的需要，调试好了，便可在github上作生产/构建/发布。

```
可以通过上传源码编译一次的方式同时获得带进度显示支持的inst.sh，和onekeydevdesk镜像包，这二者组成的仓库。
编译一次就可以获得inst.sh了。无需重复编译。
构建后的github可同步到gitee，这样你在国内国外都有同一份构建结果支持国内外主机DD。
注意：不要滥用github和gitee的服务
```

编译方式获得onekeydevdesk
--------

与github有关的工作流文件都集成在源码.github/workflows/main.yml下，因为以.开头，在osx下这是个隐藏文件，请去除隐藏后查看。

你需要事先准备二个github仓库：一个用于托管构建结果的仓库。在.github/workflows/main.yml里你可以看到这是minlearn/onekeydevdesk.git，修改它为自己的用户名。！！这个仓库设为公开，因为它是你要使用的。
还有一个就是将onekeydevdeskbuild源码包.zip解压后上传到github上的构建仓库,建议直接用onekeydevdeskbuild为仓库名，如何上传源码建立仓库这里就不讲解了。！！！切记：这个仓库要设为私有
这二个仓库，mindevdesbuild就是构建来源，onekeydevdesk就是结果。

你还需要在github帐号里的设置下生成一个名为MINLEARNPROGRAMMINGBUILD_PERSONAL_ACCESS_TOKEN的访问令牌，然后填在onekeydevdeskbuild仓库设置的Actions secrets里。

这样就可以开始了。

点开onekeydevdeskbuild仓库，修改ci.sh中开头的export autoDEBMIRROR1和export autoIMGMIRROR1二行为你自己的github用户名。

```
目前包含6个workflow文件，分别生成一个主onekeydevdesk库和5个lxc库，你可以分析出ci.sh的调用方式

usage: ci.sh [[-b 0 ] -h 0] -t onekeydevdesk[,lxcxxx+/lxcxxx++]|lxcxxx|tdl|debianbase  # lxcxxx no+: pure standalone pack mode,+: mergemode into 01-core,++: packmode into 01-core

```


点开onekeydevdeskbuild仓库的actions标签，点all workflows下的minlearnprogrammingbuild，run workflows,手动触发一次构建。

进度跑到100%之前你可以在窗口里看构建过程。

完成后，你就可以看到onekeydevdesk仓库有内容了。可以直接使用它了。
也可sync到gitee,同样在使用前记得修改inst.sh中开头的export autoDEBMIRROR1和export autoIMGMIRROR1二行为你自己的github用户名。

！！使用完后请把onekeydevdesk设为私有。



手动添源码
-----

你也可以找一份免费的inst.sh，或moeclud的源码，将显进度支持代码添加入这些脚本中，让它们也支持DD显进度功能。


