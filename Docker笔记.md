## Docker笔记

docker 安装mysql：

1. **docker search mysql**

2. **docker pull mysql**

3. **docker run --name mysql-name -e MYSQL_ROOT_PASSWORD=password -d mysql:tag**

   **docker pull [选项] [Docker Registry地址]<仓库名>:<标签> **

   - Docker Registry地址： 地址的格式一般是 <域名/IP>[:端口号] 。 默认地址是 Docker Hub。

   - 仓库名： 仓库名是两段式名称， 既 <用户名>/<软件名> 。 对于 Docker Hub， 如果不给出用户名， 则默认为 library ， 也就是官方镜像。

   - 标签: 如果不指定tag(类似:8.0)，那么docker默认会为我们加上latest

     简单运行镜像：**docker run --name mysql-name -e MYSQL_ROOT_PASSWORD=password -d mysql:tag**

     - name : mysql镜像运行容器名称

     - d : 守护进程方式运行镜像

     - e : 镜像系统变量设置，如上面例子MYSQL_ROOT_PASSWORD 设置MySQL root密码 ，详情变量可以查看镜像说明。

     - tag: 指定运行image标签，不写默认就运行laster，像MySQL这类镜像tag 多为版本号，支持多个版本MySQL运行

     - 将容器内3306端口映射到主机上3306，使用方式 -p 主机端口:容器端口

       进入镜像： **docker exec -it mysql-server mysql -u root -p **

       ![preload](https://ask.qcloudimg.com/http-save/yehe-7565276/6lldlbgfhn.png)