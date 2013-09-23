<h2><font size="16" color="blue">How can access the Web Server behind the firewall on Win7</font></h2>
========================

### ping

I do not know why local PC can not be pinged, and do not know it work.
Do somethings like following,

* start the 'SSDP Discovery' service;
* open the '启用网络发现' in '高级共享设置'
* open the '文件和打印机共享(回显请求 - ICMPv4-In)'

Ping ok now,
but why I close all above, ping work ok.

...

### behind win7 firewall and ESET6

1. select filter mode with '自动过滤模式下的排除（用户定义的规则）'
2. add a rule with local port(80/8080), remote IP:port, protocal(TCP) , orientation(two-way)

