Memo to redis
=====================


run on WIN
---------
下载redis_win.zip，解压后，在目录中创建redis.conf。
**启动redis：**
在命令行输入

    redis-server.exe redis.conf

**客户端连接**
在命令行输入

    redis-cli.exe -h localhost -p 6379

run on CentOS
---------
Download, extract and compile Redis with:

    ]# wget http://download.redis.io/releases/redis-2.8.6.tar.gz       
    ]# tar xzf redis-2.8.6.tar.gz     
    ]# cd redis-2.8.6  
    ]# make
    
Run Redis with:

    ]# src/redis-server 

master-slave
---------
在从server上打开如下配置，指向主服务器

    # slaveof <masterip> <masterport>

密码管理
---------

配置文件参数说明:
---------




> **SEE MORE:** 
>
> - about **run on WIN**  [here][1],
> - about **run on CentOS** [here][2],
> - about **master-slave**  [here][3],
> - about **密码管理**  [here][4],
> - about **配置文件参数说明** [here][5],

  [1]: http://www.newasp.net/soft/67186.html#downloads
  [2]: http://redis.io/download
  [3]: http://www.cnblogs.com/ayanmw/p/3144386.html
  [4]: http://blog.csdn.net/lxpbs8851/article/details/8136126
  [5]: http://zheng12tian.iteye.com/blog/1471726