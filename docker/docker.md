# Docker

## 1.docker概念
#### 1.1仓库
#### 1.2镜像
#### 1.3容器

## 2.docker命令（以nginx镜像为例）
#### 2.1 docker搜索镜像
```apple js
docker search nginx
```

#### 2.1 docker获取镜像
```apple js
docker pull nginx
```
#### 2.5 查看所有docker镜像
```apple js
docker images
```

#### 2.1 docker删除镜像
```apple js
docker rmi nginx
```

#### 2.1 保存修改的docker容器为新的镜像（新镜像名字为nginx-newOne）
```apple js
docker commit -m '提交信息' CONTAINER ID nginx-newOne
```
还有一种方式是通过文件dockerfile来创建新的镜像
```apple js
// 创建dackerfile
touch Dockerfile

// 写dockerfile内容
FROM alpine:latest
MAINTAINER xbf
CMD echo "this is my first dockerfile"

// 生成docker镜像
docker build -t first_docker .

// 检查是否镜像是否生成
docker images

// 运行这个镜像
docker run first_docker

// 乐意发现打印出了 this is my first dockerfile

/**
* 参数说明
* -t first_docker是给新建的docker一个叫first_docker的名字
* . 指定路径(必须是个文件夹)，当然得把dockerfile包含在内
/ 
```

#### 2.6 查看所有的docker容器
```apple js 
docker ps -a
```
 
#### 2.3 查看正在运行的docker容器
```apple js
docker ps
```

#### 2.4 运行docker容器
```apple js
docker run nginx
```

#### 2.4 停止运行docker容器
```apple js
docker stop CONTAINER ID

```
#### 2.4 docker删除容器
```apple js
docker rm CONTAINER ID
```

#### 2.4 将本地（host）文件拷贝到某个容器的指定目录下
```apple js
docker cp 本地文件 CONTAINER ID://xxx/xxx/xxx(docker路径)
```


#### 2.2 端口映射
nginx默认80端口，

这个命令的意思是将本地访问的8999端口转到80端口。

也就是说当你在页面上输入localhost:8999时候，实际上访问的是localhost:80
```apple js
docker run -p 8999:80 -d nginx
```



## 3.注意
docker 在容器内的改变都是暂时的，不会被保留下来，也就是说容器停止后再启动回没有之前的改动，除非将改动保存在镜像中