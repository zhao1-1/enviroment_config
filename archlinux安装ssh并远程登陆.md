## 1.  安装ssh

`sudo pacman -S openssh`

## 2. 启动ssh

### （1）开机启动

`systemctl enable sshd.service`

### （2）手动开启

`systemctl start sshd.service`

### （3）重启

`systemctl restart sshd.service`

## 3. ArchLinux默认不允许任何计算机远程登陆

### （1）允许所有计算机远程登录

```shell
$ touch /etc/hosts.allow
$ sudo vim /etc/hosts.allow
sshd: ALL : ALLOW
```

### （2）允许特定主机连接

```shell
$ touch /etc/hosts.allow
$ sudo vim /etc/hosts.allow
sshd:192.168.1.100:ALLOW
# 我的mac主机ip地址
sshd:192.168.2.206
# 我的腾讯云ip地址
sshd:111.229.57.47
```



## 4. 禁止所有计算机远程登陆

`touch /etc/hosts.deny`



## 5. 添加root用户

```shell
$ sudo passwd root
# 设置用户名密码即可

$ su root
# 切换root用户

$ exit
# 退出root用户
```



## 6. openssh默认不允许root帐户直接登录

```shell
$ sudo vim /etc/ssh/sshd_config
将PermitRootLogin后改成yes，并将其前的#号去掉就可以了.   //也可以直接在修改文件最后加上
```

修改之后就允许以root身份远程登陆了。



## 7. 重启ssh服务

`systemctl restart sshd`