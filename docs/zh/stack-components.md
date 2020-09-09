---
sidebarDepth: 3
---

# 参数

Ghost 预装包包含 Ghost 运行所需一序列支撑软件（简称为“组件”），下面列出主要组件名称、安装路径、配置文件地址、端口、版本等重要的信息。

## 路径

### Ghost

Ghost 安装目录： */data/wwwroot/ghost/content*  
Ghost 配置文件： */data/wwwroot/ghost/config.production.json*  
Ghost 容器编排文件： */data/wwwroot/ghost/docker-compose.yml*  

### Nginx

Nginx 虚拟主机配置文件：*/etc/nginx/conf.d/default.conf*  
Nginx 主配置文件： */etc/nginx/nginx.conf*  
Nginx 日志文件： */var/log/nginx*  
Nginx 伪静态规则目录： */etc/nginx/conf.d/rewrite*

### MySQL

MySQL 安装路径: */usr/local/mysql*  
MySQL 数据文件 */data/mysql*  
MySQL 配置文件: */etc/my.cnf*  

### phpMyAdmin

采用容器的方式运行 phpMyAdmin， 环境与 Ghost 容器隔离，稳定可靠。  

访问方式： *http://服务器公网IP：9090*


### Docker

Docker 根目录: */var/lib/docker*  
Docker 镜像目录: */var/lib/docker/image*   
Docker daemon.json 文件：默认没有创建，请到 */etc/docker* 目录下根据需要自行创建   


## 端口号

在云服务器中，通过 **[安全组设置](https://support.websoft9.com/docs/faq/zh/tech-instance.html)** 来控制（开启或关闭）端口是否可以被外部访问。 

通过命令`netstat -tunlp` 查看相关端口，下面列出可能要用到的端口：

| 名称 | 端口号 | 用途 |  必要性 |
| --- | --- | --- | --- |
| HTTP | 80 | 通过 HTTP 访问 Ghost | 可选 |
| HTTP | 443 | 通过 HTTPS 访问 Ghost | 可选 |
| TCP | 9090 | 数据库可视化管理工具 phpMyAdmin | 可选 |
| TCP | 3306 | 本地数据库客户端访问数据库 | 可选 |

## 版本号

组件版本号可以通过云市场商品页面查看。但部署到您的服务器之后，组件会自动进行更新导致版本号有一定的变化，故精准的版本号请通过在服务器上运行命令查看：

```shell
# Check all components version
sudo cat /data/logs/install_version.txt

# Linux Version
lsb_release -a

# Nginx  Version
nginx -V

# Node version
node -v

# Docker Version
docker -v

# MySQL  Version
mysql -V

# Node  Version
sudo docker exec -it ghost /bin/bash -c 'node -v'

# Ghost version
sudo docker exec -it ghost /bin/bash -c 'ls versions'
```