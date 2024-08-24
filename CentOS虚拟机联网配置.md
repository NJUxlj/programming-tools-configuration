
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

