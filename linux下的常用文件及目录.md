Linux 常见文件及目录1.0（运维人员必看）
基于 RHEL6

/etc/ 系统主要的配置文件存放目录
     /etc/passwd	用户的基本信息，包括用户的用户名，UID,GID,用户信息说明,用户的主文件夹，用户的Shell等信息
　　　/etc/group	用户组基本信息，包括用户组名称，GID，用户组支持的用户帐号等信息
　　　/etc/shadow 	/etc/passwd 文件的补充，早期用户的密码保存在/etc/passwd里面，后来为了安全，就将密码保存到此文件里面，/etc/passwd里用x代替密码。包括帐号名称，密码，最近改动密码的日期，密码不可被改动的天数，密码需要重新更改的天数，密码需要更改期限前的警告天数，密码过期后的帐号宽限时间，帐号失效日期等信息。
　　　/etc/gshadow	阴影口令套组中的组配置文件
　　　/etc/login.defs		设置用户帐号限制的文件，在这里我们可配置密码的最大过期天数，密码的最大长度约束等内容。该文件里的配置对root用户无效。如果/etc/shadow文件里有相同的选项，则以/etc/shadow里的设置为准，也就是说/etc/shadow的配置优先级高于/etc/login.defs
　　　/etc/securetty		列出的虚拟控制台确定允许root用户可以登录，意思就是里面列出的都是root用户可以从上面登录的。
　　　/etc/securetty/access.conf	控制所有用户的访问
　　　/etc/bashrc	用于系统范围内的别名和函数
　　　/etc/profile	此文件为系统的每个用户设置环境信息,当用户第一次登录时,该文件被执行. 并从/etc/profile.d目录的配置文件中搜集shell的设置. 
     /etc/opendap/slapd.conf 	LDAP服务器的主配置文件
　　　/etc/pam_ldap.conf		LDAP 客户配置
　　　/etc/openldap/ldap.conf	LDAP 配置拓展
　　　/etc/crontab		cron 是一个可以用来根据时间、日期、月份、星期的组合来调度对重复任务的执行的守护进程，而此文件就是其配置文件。内容详见：http://blog.csdn.net/foxman209/article/details/6759920
     /etc/xinetd.conf	保存 xinetd 服务的通用配置
　　　/etc/fstab 	在引导期间挂载的文件系统的标准配置文件
　　　/etc/auto.master	/misc/目录的配置文件
　　　/etc/auto.misc	自动挂载器autofs的配置文件，关于autofs详见：http://blog.csdn.net/m582445672/article/details/7885477
　　　/etc/auto.net		查看和读取共享的 HFS 目录
     /etc/auto.smb  	在不需要用户名和口令的共享目录起作用
　　　/etc/auto.home	设置共享目录相关文件
　　　/etc/yum.conf	基于 yum 的配置文件
　　　/etc/sysconfig/network6	简单的网络配置内容
　　　/etc/sysconfig/network-scripts/ifcg-lo		回环地址信息
　　　/etc/nsswitch.conf 	定义了从认证到名称服务器的所有内容的的数据库搜索条目
详见：http://wPostfix维护与管理技巧ww.cnblogs.com/cute/archive/2012/05/17/2506342.html
　　　/etc/hosts	保存了主机名和它们的 IP 地址，功能详见：http://blog.sina.com.cn/s/blog_6714fba701018pip.html
　　　/etc/resolv.conf	记录了 DNS 服务器的位置
　　　/etc/sysconfig/init		文件中的参数指定了系统在引导过程中的外观和体验,关于/etc/sysconfig/目录详见：http://blog.chinaunix.net/uid-793704-id-2545546.html
　　　/etc/init/control-alt-delete.conf	定义按下Ctrl-Alt-Del 重启系统功能的文件,系统启动时调用，详见：https://linux.cn/article-3976-1.html
　　　/etc/init/plymouth		取代图形化系统
　　　/etc/init/readahead-collector.conf	记录启动时预读取的文件
　　　/etc/init/readahead-disable-services.conf	记录启动时禁止预读取的文件
　　　/etc/init/readahead.conf	实际启动 readahead 进程
　　　/etc/init/prefdm.conf		启动并管理运行级 5 的 GUI 登录
　　　/etc/init/start-ttys.conf		启动全部终端
　　　/etc/init/tty.conf	另一个终端名称
　　　/etc/init/serial.conf	当通过串行端口建立连接时使用此文件
　　　/etc/init/rcS.conf	在引导过程中执行/etc/rd.d/rc.sysinit 脚本
　　　/etc/init/rcS-sulogin.conf	在单用户模式下启动使用一个终端
　　　/etc/init/rc.conf	在运行时执行脚本,被执行的脚本保存在/etc/rcn.d/目录中
　　　/etc/inittab	itit的配置文件，init根据/etc/inittab配置文件来执行相应的脚本进行系统初始化,如设置键盘、字体,装载模块,设置网络等。
　　　/etc/hosts.allow	TCP包装器的同意列表
　　　/etc/hosts.deny	TCP包装器的拒绝列表，关于/etc/hosts.allow 和 /etc/hosts.deny 参见 http://blog.sina.com.cn/s/blog_53da0ca70101dewe.html
　　　/etc/sysctl.conf 	一个允许改变正在运行中的Linux系统的接口，它包含一些TCP/IP堆栈和虚拟内存系统的高级选项，修改内核参数永久生效。也就是说/proc/sys下内核文件与配置文件sysctl.conf中变量存在着对应关系。
     /etc/postfix/
　　　	/etc/postfix/relocated	包含外部网络用户的信息
　　　	/etc/postfix/transport	在需要转发邮件的情况下很有用
　　　	/etc/postfix/virtrual	将电子邮件转发给本地系统上的用户账户
　　　	/etc/postfix/main.cf	Postfix 主要配置/etc/sysconfig/目录　
     /etc/sysconfig/network-scripts/	存储关于网络配置的脚本文件
　　　/etc/rcn.d/	开机时被自动执行的脚本
　　　/etc/yum/pluginconf.d/		关于 yum 文件的配置
　　　/etc/yum.repos.d/		里面的配置文件用来连接系统和实际库
　　　/etc/skel/			包含新账户的默认环境文件
　　　/etc/profile.d/		用来包含/etc/profile 文件要执行的脚本
　　　/etc/cron.d			描述计算机的定期任务
　　　/etc/xinetd.d/		里面的每个文件都为 xinetd 指定一个要管理的特点服务
     /etc/ssh/		存储 SSH 服务配置文件
/usr/
　　　/usr/share/doc/	各软件设计者的文档
/proc/
　　　/proc/sys/		存储内核运行的参数
