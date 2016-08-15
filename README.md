# centos6.5-mongodb3.2
在centos6.5下安装mongodb3.2

(虽然网上教程好多可是都太老了，使用起来失败的多，链接方法可能都不可以用了)

最近在centos6.5下开发nodejs，需要安装mongodb，然后就从网上找教程

发现了许多教程，发现用yum下安装mongodb最简单然后就开始安装教程做

但是失败了没有成功，然后心想算了去mongodb找教程安装，还真发现了，

结合网上的资源和官网的教程来安装最新版的mongodb3.2

1、创建repo

vi /etc/yum.repos.d/mongodb-org-3.2.repo


[mongodb-org-3.2]

name=MongoDB Repository

baseurl=https://repo.mongodb.org/yum/amazon/2013.03/mongodb-org/3.2/x86_64/

gpgcheck=1

enabled=1

gpgkey=https://www.mongodb.org/static/pgp/server-3.2.asc

2、安装MongoDB和相关工具

yum install -y mongodb-org

3、启动MongoDB

sudo service mongod start

4、验证MongoDB是否启动成功

cat /var/log/mongodb/mongod.log

查看是否有一句：[initandlisten] waiting for connections on port <port>

其中<port>是在/etc/mongod.conf中配置的，默认情况下是27017端口。

5、使MongoDB开机自动启动

sudo chkconfig mongod on

6、停止MongoDB

sudo service mongod stop

7、重启MongoDB

sudo service mongod restart

8.完成
