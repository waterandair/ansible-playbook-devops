#### 6379.conf 是 redis 的配置文件
##### 配置的内容有:
```
daemonize	yes							让redis以daemon进程运行
pidfile		/var/run/redis_6379.pid 	设置redis的pid文件位置
port		6379						设置redis的监听端口号
dir 		/var/redis/6379				设置持久化文件的存储位置
# bind 127.0.0.1                        注释掉 bind , 是所有网络可连
```

#### redis 文件是redis启动脚本取自 redis安装目录下 utils中的 redis_init_script
##### 脚本中加入以下内容
```
### BEGIN INIT INFO
# Provides:          redis6379
# Required-Start:    $local_fs $network
# Required-Stop:     $local_fs
# Default-Start:     2 3 4 5
# Default-Stop:      0 1 6
# Short-Description: redis6379
# Description:       penavico redis 6379
### END INIT INFO
```
