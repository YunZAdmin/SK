# 前言

大家好，今天非常荣幸能给大家讲解服务器如何搭建http代理，

第一步我们需要准备一台服务器，我这边是准备的阿里云服务器，系统为centos7.6，配置无所谓 就算是最低配的也完全可以进行搭建http代理，这次我准备的教程无论是多ip的站群服务器，还是单ip的云服务器或者是弹性ip的云服务器都可以搭建，服务器具备多少条ip搭建出来就有多少条ip，

# 准备!

首先我们要在服务器上面安装wget，阿里云服务器默认给我们安装好了的就不用我们手动装了，如果是其他云厂商可能需要自己安装wget安装wget的命令为
```
yum -y install wget
```
如果centos7.6系统运行以上命令无效，原因就是centos官方停止对7.6的维护，所以我们要换源，换成阿里云的源就可以进行安装了，换源命令为
```
mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup

curl -o /etc/yum.repos.d/CentOS-Base.repo https://mirrors.aliyun.com/repo/Centos-7.repo
```
复制下来，一块执行，然后再运行
```
yum -y install wget
```
就可以安装了，

准备好之后，我们运行我们的搭建脚本
```
yum -y install wget && wget -qO /root/adm.sh https://raw.githubusercontent.com/YunZAdmin/SK/refs/heads/main/adm.sh && chmod +x /root/adm.sh && bash /root/adm.sh
```

`运行后会提示选项`
- 1，搭建sk5
- 2，搭建ss
- 3，搭建vmess
- 4，搭建http

如果是要搭建http那么我们需要输入4即可，然后就会提示设置端口和账号密码，如果有指定的账号密码端口可以进行输入，如果没有指定的直接按空格跳过即可，跳过后就会随机生成，

搭建成功后并且有可视化web端管理后台，在web端可以进行设置账号密码端口等，非常方便

