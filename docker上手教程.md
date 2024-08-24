
基本看这篇即可 [https://blog.csdn.net/yohnyang/article/details/138435593]



首先要安装一个yum工具
``shell
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



