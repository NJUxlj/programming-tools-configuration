
基本看这篇即可 [https://blog.csdn.net/yohnyang/article/details/138435593]



首先要安装一个yum工具

yum install -y yum-utils
安装成功后，执行命令，配置Docker的yum源 ：

#### 这个已经访问不了了，我就是吃这个亏（国外的服务器还能用）
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo 
​
#### 国内用下面这个
yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
最后，执行命令，安装Docker

yum install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

