
基本看这篇即可 [https://blog.csdn.net/yohnyang/article/details/138435593]



首先要安装一个yum工具
```shell
yum install -y yum-utils
```

安装成功后，执行命令，配置Docker的yum源 ：

#### 这个已经访问不了了，我就是吃这个亏（国外的服务器还能用）
```shell
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```
​
#### 国内用下面这个
```shell
yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
```

最后，执行命令，安装Docker
```shell
yum install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```



非root权限：
```shell
sudo systemctl enable docker
sudo systemctl start docker
```

root权限：
```shell
systemctl enable docker
systemctl start docker
```

启动Docker
```shell
sudo systemctl enable docker
sudo systemctl start docker
```


验证安装是否成功
```shell
docker run hello-world
```

docker run hello-world会先从本地搜索名为hello-world的镜像，若没有找到，则先从docker hub中pull该镜像，拉取镜像到本地成功后，再通过run指令来启动容器运行该镜像。



```shell
C:\Users\lynnh>docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
0e03bdcc26d7: Pull complete
Digest: sha256:7f0a9f93b4aa3022c3a4c147a449bf11e0941a1fd0bf4a8e6c9408b2600777c5
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:

$ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/


```




### Linux配置Clash代理
[https://zhengyang.wang/2022/03/linux-config-clash/]









### 解决yum报错：错误：Invalid version flag: if
[https://www.cnblogs.com/guuyoog/p/17666449.html]



### 【环境配置】VMware虚拟机使用主机代理（详细教程）
[[https://blog.csdn.net/qq_34207422/article/details/136745344](https://blog.csdn.net/weixin_63594197/article/details/138069939)]



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
