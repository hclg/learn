# linux各种常用操作

### 1. 静态ip配置

* ip地址 
* 子网掩码
  * 子网掩码只有一个作用，就是将某个IP地址划分成[网络地址](https://baike.baidu.com/item/网络地址/9765459)和[主机地址](https://baike.baidu.com/item/主机地址/9765500)两部分
* 默认网关
  * 是计算机网络中一个如何将数据包转发到其他网络中的节点。

#### 1.1 网络配置文件

| 路径及文件名                    | 功能                                                 |
| ------------------------------- | ---------------------------------------------------- |
| /etc/hosts                      | 完成主机名映射为IP地址的功能                         |
| /etc/hostname                   | 记录主机名 hostnamectl set-hostname 主机名 #永久修改 |
| /etc/sysconfig/network-scripts/ | 网卡的配置文件目录如ifcfg-ens33      ,ifcfg-*        |
| /etc/resolv.conf                | 设置DNS服务器IP地址的配置文件                        |

#### 1.2网卡配置

```bash
DEVICE=当前网卡设备名称
BOOTROTO=static|none|dhcp IP获取方式
		静态|引导是不用协议|bootp协议/dhcp协议
BRPADCAST=X.X.X.255 广播地址
HWADDR=00:0C:29:6A:08:39 MAC地址
IPADDR = IP地址
PREFIX=24 子网掩码
GATEWAY= 网关
DNS1= 
ONBOOT=yes 开机自动启动

###上面配置好了
ifdown 网卡 关闭
ifup 网卡 打开
```

### 2. 添加用户

```bash
cat /etc/passwd #查看用户信息
userdel -r 用户 #删除用户
useradd 用户名 #添加用户
passwd 用户 配置密码
# 配置免密登陆
ssh-keygen -t rsa #生成密钥
cd ~/.ssh/ #密钥的存放位置
ssh-copy-id -i ip

```

