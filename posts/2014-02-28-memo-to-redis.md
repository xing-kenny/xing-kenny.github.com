Memo to redis
=====================


run on WIN
---------
下载redis_win.zip，解压后，在目录中创建redis.conf。
**启动redis：**
在命令行输入

    redis-server.exe redis.conf

run on CentOS
---------
Download, extract and compile Redis with:

    ]# wget http://download.redis.io/releases/redis-2.8.6.tar.gz       
    ]# tar xzf redis-2.8.6.tar.gz     
    ]# cd redis-2.8.6  
    ]# make
    ]# make test
    You need tcl 8.5 or newer in order to run the Redis test
    //install tcl, 
    ...
    ]# make test
    ...
    ]# src/redis-server 

more about **install tcl** , see [here][6],


关闭redis
---------
    # redis-cli shutdown //关闭所有
    关闭某个端口上的redis
    # redis-cli -p 6397 shutdown //关闭6397端口的redis


**客户端连接**
---------

在命令行输入

    redis-cli.exe -h localhost -p 6379

master-slave
---------
在从server上打开如下配置，指向主服务器

    # slaveof <masterip> <masterport>

密码管理
---------
> [here][4]

配置文件参数说明
---------
> [here][5]

jedis-2.4.1
---------

		JedisShardInfo info = new JedisShardInfo("localhost");
		info.setPassword("kenny");
		Jedis jedis = new Jedis(info);
		jedis.set("foo", "bar");
		String value = jedis.get("foo");		
		logger.info("value = " + value);
		jedis.close();

install as service
---------
> [here][7]




----------

> **SEE MORE:** 
>
> - more about **run on WIN**  [here][1],
> - more about **run on CentOS** [here][2],
> - more about **master-slave**  [here][3],
> - more about **密码管理**  [here][4],
> - more about **配置文件参数说明** [here][5],
> - more about **install as service** [here][7],
> - more about **install as service**,this is a script which works on CentOS, and can be used in provious doc's step 9&10 , [here][8],


  [1]: http://www.newasp.net/soft/67186.html#downloads
  [2]: http://redis.io/download
  [3]: http://www.cnblogs.com/ayanmw/p/3144386.html
  [4]: http://blog.csdn.net/lxpbs8851/article/details/8136126
  [5]: http://zheng12tian.iteye.com/blog/1471726
  [6]: http://www.linuxfromscratch.org/blfs/view/cvs/general/tcl.html
  [7]: http://www.saltwebsites.com/2012/install-redis-245-service-centos-6
  [8]: https://gist.githubusercontent.com/paulrosania/257849/raw/9f1e627e0b7dbe68882fa2b7bdb1b2b263522004/redis-server