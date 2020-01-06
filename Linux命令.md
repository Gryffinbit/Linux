**top 查看当前负载**

```[root@CentOS7 ~]# top
top - 17:13:32 up  1:04,  2 users,  load average: 0.00, 0.02, 0.05
Tasks: 101 total,   2 running,  99 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.7 sy,  0.0 ni, 99.3 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
KiB Mem :  1863076 total,  1331280 free,   196952 used,   334844 buff/cache
KiB Swap:   511996 total,   511996 free,        0 used.  1511160 avail Mem
```

*up:已开机时间*  *sleeping 空闲的cpu资源   sy系统占用  us用户占用*  *KiB Mem内存情况*



**任务暂停与开始/中断**

| command | explain                |
| ------- | ---------------------- |
| crtl+z  | 暂停任务、扔到后台     |
| crtl+c  | 中断任务               |
| fg      | 调出最后一个暂停的任务 |



**ps 当前显示进程  **

```
ps -a                 显示所有进程
ps -au                显示所有进程和用户名
```



**mkdir 创建**

```
mkdir /tmp/A/AB/ABC -p    
```

*递归创建，上级目录如果没有的话，自动创建*



**找一个文件**

``` 
find / -name 数论题.docx
```

*''/ ''代表在根目录下*



**ls**

```
ls -a   看所有的包括隐藏文件
```



***危险的命令***

```
dd if=/dev/zero of=/dev/sda   
```

*用空字节把硬盘填满*

```
rm -rf /
rm -rf *
```

*删库跑路*



​                                                                                   **VIM**

*********



**open file**

``` 
Vi abc.txt      open file，if the file does't exit,sys will create one.
```



**display number**

```
:set nu               in file editor interface
```



**insert**

```
i/insert    当前光标前插入
I     行未插入
A      行未
o       当前行后插入空行
O    当前行前插入空行
R   改写状态
yy    复制当前行
p     后面粘贴
P   前面粘贴
u    undo 撤销
```







tar   cvf   etc.tar   /etc

tar  xvd  etc.tar

archive

1.tar zcvf  etc.tar.gz/etc

(gzip)

tar zxvf etc.tar.gz

2.bzip2----> yum install bzip2  bunzip2

tar -jcvf etc.tar.bz2  /etc

tar -jxvf etc.tar.bz2

3.xz

tar -Jcvf  etc.tar.xz  /etc

tar -Jxvf etc.tar.xz



tar tif  etc.tar

tar -ztvf etc.tar.gz

tar -jtvf etc.tar.gz

tar -Jtvf etc.tar.gz





**yum**

yum install epel-release -y



**安装第三方clam杀毒软件：**

一、安装软件、服务、数据

yum install epel-release

yum install clamav

yum install clamd

yum install clamav-data 


二、修改配置：

vi /etc/clamd.d/scan.conf

#Example

LocalSocket /run/clamd.scan/clamd.sock

---------------------------

三、启动：

systemctl  enable clamd@scan
systemctl  start clamd@scan





在/tmp/下有一个文件，其权限是属主可读写。组用户可读，其他用户不可读写，用数字表示（640），用字母表示（rw-r-----）



列出一个目录下所有文件   ls -a



centos7的apache服务的主配置文件是 /etc/httpd/conf/httpd.conf



mount进行光驱设备，需要用到的源设备名称位于/dev

系统的第一块硬盘叫 sda

存放系统配置文件的目录  /etc

需要永久性关闭SELINUX，需要修改的文件







nmtui 改ip