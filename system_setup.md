### legency启动模式下安装Windows和Ubuntu双系统（ssd+hhd）:
1、参考的文章如下[legency启动模式下安装Windows和Ubuntu双系统](https://blog.csdn.net/chaixingsi/article/details/86722410#01__5)

2、双硬盘安装分区，boot安装在ssd中和win一块，需要在Windows中把ssd分一块300-500m大小的分区

3、安装Ubuntu时候，只需要分两个盘符就行一个/30G一个/home80G，另外将ssd中的那块划分为/boot。最下面的引导管理选择有boot的那个盘

4、安装Ubuntu完成会进行重启，此时会直接进入win10中，需要用easybcd引导下，参考文章中只需要更改一个地方就可以，只要把最后保存设置前，把跳过启动界面取消就行，这样就会直接进入Ubuntu的引导界面，不这样设置的话，会导致先进入Windows的引导界面，然后在进入Ubuntu的引导界面。

5、进入Ubuntu18.04，会提示更新，这时候不要着急，先更换速度更快的国内源，选择软件和更新选项中，找到下载来自，选择其他，在中国的选项卡中选择国内的源，有清华、中科大、阿里云等等，还有我们上大的源可以使用。

6、开始配置我们的ubunut机器。首先连接无线。

7、[安装中文输入法](https://baijiahao.baidu.com/s?id=1619306801356144376&wfr=spider&for=pc)

8、修复系统下中文显示不全的问题，是因为系统配置文件中优先显示日文，需改配置文件。参考[修复Ubuntu中文字体只显示一半的问题](https://blog.csdn.net/szsteel1/article/details/55540740)

9、[安装atom](https://www.sysgeek.cn/ubuntu-1804-install-atom/)
上面的这种方式比较简单，，可以直接命令行启动，然后就是配置主题和markdown的编辑插件即可。更换下源，
  - sudo gedit ~/.atom/.apmrc
  - 添加一下文本到文件中去：registry=https://registry.npm.taobao.org

10、安装git

11、安装pycharm，[进行激活](http://idea.lanyus.com/)

12、基本上atom+pycharm就够了学习Python的了

13、[测试Linux下的网速](http://www.linuxde.net/2014/01/15561.html)

14、利用pyvenv创建虚拟环境，并且配置机器学习、opencv、深度学习环境。

15、配置深度学习环境时，安装的tensorflow版本是[cpu版本](https://tensorflow.google.cn/install)(是因为gpu太垃圾了懒得弄了。)

16、进入pycharm选择使用的虚拟环境就可以进行使用。

17、使用git时候出现了远程仓库不能允许的问题，重新删除再安装git之后发现atom炸了，之后去官网查看installation部分进行下载安装，比较方便。

18、现在可以开始开始进行学习Linux的基础学习。
学习操作系统一定要心细，认真思考每一步的想法。

19、

### Ubuntu18.04出现的问题以及解决方法：

1、使用几天过后出现Windows进不去，解决方法是不进去就行了，恨不得只用Ubuntu呢，但是一般进不去一是grub找不到win的引导，可以参考网上的教程进行修改启动配置文件，另一个方面是引导文件损坏，这两种都可以通过百度查找解决方案，但是如果还是不行的话，就等待或者直接重装双系统了。目前只是水平有限，解决问题的方式也仅限于这些。

2、出现Ubuntu卡顿，关机之后进不去Ubuntu，表现为开机没有启动项，直接黑屏闪烁光标，这时候将系统boot所在的盘添加为启动盘。通过前面安装的U盘进入，选择试用Ubuntu，在命令行使用下面命令：
- sudo fdisk -l找到后边为Linux 的盘符进行挂载
- sudo mount /dev/sda1 /mnt比如这样

- sudo grub-install --boot-directory=/mnt/ /dev/sda1

- reboot

重启可以发现不出意外可以进入Ubuntu系统，但是上面的双系统win进不去不知道可不可以通过这种方式进入
**let`s get it！**
