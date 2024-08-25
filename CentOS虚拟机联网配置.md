
基本上看这篇就行(这里)[https://blog.csdn.net/2301_80064376/article/details/140835874]


### 什么是宿主IP
就是你电脑的ip
使用控制台 ipconfig可以查看
或者在你当前连接的无线网配置中查看（电脑右下角设置）


### 什么是NAT网关


### 如何查看虚拟机上的网络配置
1. 在控制台中查看
```shell
sudo vi /etc/sysconfig/network-scripts/ifcfg-ens33
```
2. 在虚拟机最上方任务栏中查看
  
![image](https://github.com/user-attachments/assets/c2726ac5-9766-4de8-af55-fd84cb63ad8b)
![image](https://github.com/user-attachments/assets/b409ccdf-570b-4070-ae47-853ee1654239)
![image](https://github.com/user-attachments/assets/f01c49c4-ea6c-4063-bca6-0f935b6cd445)


### 什么是虚拟机IP
```shell
ip addr
```




### 如何判断有没有连上网
ping www.baidu.com
通了即可





## 在CentOS虚拟机中开启代理（如Clash之类）
检查DHCP设置，没问题即可，当前我的NAT网关是192.128.2.2，子网是192.128.2.0, 虚拟机IP是192.128.2.88, 宿主机IP是 192.128.2.123

![image](https://github.com/user-attachments/assets/a0776774-14f8-4b27-b34b-b4fbd169f7cc)

![image](https://github.com/user-attachments/assets/abfd6167-656d-4724-ae2a-110f270b5bcc)








## Ubuntu中安装 Docker
[https://blog.csdn.net/qq_61183213/article/details/139802898]
sudo apt-get update
sudo apt-get upgrade


#### 安装Docker依赖
apt-get install \
ca-certificates \
lsb-release \
curl \
gnupg -y



#### 添加Docker密钥
curl -fsSL http://mirrors.aliyun.com/docker-ce/linux/ubuntu/gpg | sudo apt-key add -


#### 获取docker源
1. 添加当前Docker系统的代号
lsb_release -cs
>> jammy


添加Docker稳定版的官方软件源
一般情况下，Ubuntu 16.04 LTS代号为xenial，Ubuntu 18.04 LTS代号为bionic。

以Ubuntu 16.04 LTS操作系统为例，非xenial版本的系统注意修改为自己对应的代号：

sudo add-apt-repository \
"deb [arch=amd64] http://mirrors.aliyun.com/docker-ce/linux/ubuntu \
xenial \
stable"


添加成功后，再次更新apt软件包缓存

sudo apt-get update


#### 安装Docker
sudo apt-get install -y docker-ce


9、配置Docker服务
        为了避免每次使用Docker命令时都需要切换到特权身份，可以将当前用户加入安装中自动创建的docker用户组

sudo usermod -aG docker docker


sudo usermod -aG docker $USER
或者可以直接使用$USER这一bash命令替换当前用户名
