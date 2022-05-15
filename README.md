# MySQl-on-arm
在M系列芯片的Mac上使用MySQL
# M系列芯片的Mac想使用CentOS，目前无解
CentOS 7.2009 on arm最后更新在2020-11-03 10:21（镜像见http://mirror.worria.com/centosaltarch/7.9.2009/isos/aarch64/）。对Apple silicon（就是Apple自研M系列芯片）优化极其不友好，导致苹果的独家虚拟机Parallels Desktop甚至无法安装它（当然VM也不行）；CentOS8更不用说了，不仅没有优化，在保留了7的bug的同时还衍生出了新的bug。总的来说就是：用上M系列芯片的Mac无法使用虚拟机作为服务器以及使用宝塔进行一键式管理。所以当前最优解就是：将所用的Mac直接当做服务器来用（Parallels Desktop上安装macOS的虚拟机也是可以的。当然，如果你会使用乌帮图也是可以的，因为它是基于Linux开发的图形化系统，保留了CentOS的可用性）。
# 1.下载MySQL及安装
首选官网下载（个人使用选择免费的GPL，也就是社区版）：https://dev.mysql.com/downloads/mysql/
<img width="776" alt="image" src="https://user-images.githubusercontent.com/97742152/168456709-45751a39-7a44-472d-b1d1-9d3b32f9c1ec.png">
一键安装即可
# 2.配置MySQL
打开设置，MySQl就在最下方
<img width="647" alt="image" src="https://user-images.githubusercontent.com/97742152/168456764-03f6c1a4-d5f7-48ac-95c9-a5a766254331.png">
点击打开，右侧菜单栏点击Start MySQL Server。启用会要求你设置管理员密码，这很重要！（建议设置和开机密码一致）
打开终端，执行export PATH=$PATH:/usr/local/mysql/bin
终端执行mysql -uroot -p，输入管理员密码后回车，看到数据库初始化了就意味着电脑已经与数据库连接，可以对数据库进行操作了。
# 3.配置可视化操作平台
为了方便数据管理，我们将使用可视化操作平台，这边使用的是workbench https://dev.mysql.com/downloads/workbench/
<img width="1024" alt="image" src="https://user-images.githubusercontent.com/97742152/168457146-0e36b0d9-bb1f-48db-864e-131e6233a483.png">
它下载完直接用就行，它会自动查找数据库，选择对应数据库，输入管理员密码后使用。
