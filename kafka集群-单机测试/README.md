## kafka集群环境

kafka集群中的zookeeper使用官方提供的镜像进行搭建，kafka使用2.6.0的版本源码进行搭建（系统使用CentOS7.6版本）。

kafka集群中包含3个节点的zk节点，IP地址分别是10.10.10.31/32/33，kafka也包含三个节点，分别是10.10.10.41/42/43。

集群中的六个服务器节点会加入名称为app_net的网络（在本地服务搭建中创建的）

三台kafka节点的9092端口分别映射到宿主机的：9092/9093/9094端口



安装docker-compose

```bash
cd **/kafka-cluster
cp docker-compose-Linux-x86_64 /usr/local/bin/docker-compose

# 赋予脚本执行权限
chmod +x /usr/local/bin/docker-compose
```

启动集群

```bash
#启动集群，首次运行会自动编译kafka进行，创建一个名称为kafka2.6.0的镜像
docker-compose up -d
```

