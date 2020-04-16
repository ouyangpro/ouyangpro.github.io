### jvisualvm工具性能监控部署方法

#### 1、Spring Boot项目中启用jmx

在项目启动参数中新增配置如下
```
-Dcom.sun.management.jmxremote  
-Djava.rmi.server.hostname=192.168.0.227  //服务器ip(宿主机)
-Dcom.sun.management.jmxremote.rmi.port=19004  //rmi端口作为连接的数据端口
-Dcom.sun.management.jmxremote.port=19003 //jmx连接远程端口
-Dcom.sun.management.jmxremote.ssl=false //关闭ssl校验
-Dcom.sun.management.jmxremote.authenticate=false  //关闭权限校验
```
我们没有在生产服务器连接所以没有启用权限校验。

#### 2、配置端口映射

需要配置好物理机和docker虚拟机不然也是无法正常连接

#### 3、启动jvisualvm连接远程服务器
选择远程->右键添加远程主机->输入宿主机ip确定->在主机ip右键选择添加jmx连接->输入jxm远程连接端口后点击确定
![](https://adolphouyang.github.io/img/assets/jvisualvm.png)
