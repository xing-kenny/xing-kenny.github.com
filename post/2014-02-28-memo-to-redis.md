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


> **SEE MORE:** 
>
> - about **run on WIN** syntax [here][1],
> - about **run on CentOS** syntax [here][2],

  [1]: http://www.newasp.net/soft/67186.html#downloads
  [2]: http://redis.io/download
