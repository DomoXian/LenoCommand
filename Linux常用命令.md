# Linux 常用命令
#### 1、查看已安装软件
* rpm -qa  Redhat
* yum list install Redhat
* dkpg -l Debian

#### 2、传输文件命令
##### 2.1 获取远程服务器上的文件
* scp -P 端口号 服务器ip:远程目录/文件名 本地目录/文件名
> 例如：scp -P 2222 root@106.14.144.168:/root/test.txt /local/test.txt<br>
> 端口大写P 为参数，2222 表示更改SSH端口后的端口，如果没有更改SSH端口可以不用添加该参数

##### 2.2 将本地文件上传到服务器
> 例如：scp -P 2222 /local/test.txt root@106.14.144.168:/root/test.txt

#### 3、Docker命令
* docker images 查看本地镜像
* docker run [REPOSITORY] 前台运行镜像
* docker run -d [REPOSITORY] 后台运行镜像
* docker run -d -p 8888:8080 [REPOSITORY] 指定端口后台运行镜像
* docker ps 查看已经运行的镜像
#### 4、网络
* ps 命令
* netstat 命令

#### 5、文件
* mkdir命令
* touch 命令
* rm 命令
* find 命令
* cp 命令
#### 6、用户和权限
#### 7、查看内存
* free -mh
#### 8、查看系统信息
* more /etc/redhat-release 查看系统版本
* uname -r 查看内核版本
* hostname 查看主机名
* cat /etc/sysconfig/network 修改主机名
* sestatus 查看selinux情况
* 查看cpu信息
> 例如：more /proc/cpuinfo | grep "model name"
> 例如：grep "model name" /proc/cpuinfo
* 查看内存信息
> 例如：grep MemTotal /proc/meminfo
> 例如：free -m

#### 9、文件查找
* find / -name filename.txt  根据名称查找/目录下的filename.txt文件。
* find . -name "*.xml"  递归查找所有的xml文件
* find . -name "*" |xargs grep "hello"  递归查找所有文件内容中包含hello world的xml文件
* grep -H 'spring' *.xml  查找所以有的包含spring的xml文件
* find ./ -size 0 | xargs rm -f &  删除文件大小为零的文件
* ls -l | grep '.jar'  查找当前目录中的所有jar文件
* grep 'test' d*  显示所有以d开头的文件中包含test的行。
* grep 'test' aa bb cc  显示在aa，bb，cc文件中匹配test的行。
* grep '[a-z]\{5\}' aa  显示所有包含每个字符串至少有5个连续小写字符的字符串的行。
