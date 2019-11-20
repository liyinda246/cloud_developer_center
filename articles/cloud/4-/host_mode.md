# 宿主机模式

## dubbo+微服务

```shell
echo "$(ip add | grep -w inet | grep -v 127.0.0.1 | awk NR==1'{print $2}' | cut -d "/" -f 1) $(hostname)" >> /etc/hosts && java $JAVA_OPTS -Dloader.path=config -Dserver.port=$PORT0 -jar 2048.jar --server.port=$PORT0
```

**备注**：

1. 将宿主机的`hostname`写到容器的`/etc/hosts`里面

```shell
echo "$(ip add | grep -w inet | grep -v 127.0.0.1 | awk NR==1'{print $2}' | cut -d "/" -f 1) $(hostname)" >> /etc/hosts
```

2. 修改启动命令，增加`-Dserver.port=$PORT0`，让微服务启动的时候，读取到服务端口

## dubbo

```shell
echo "$(ip add | grep -w inet | grep -v 127.0.0.1 | awk NR==1'{print $2}' | cut -d "/" -f 1) $(hostname)" >> /etc/hosts && java $JAVA_OPTS -Dloader.path=config -jar 2048.jar
```

**备注**：

1. 将宿主机的`hostname`写到容器的`/etc/hosts`里面

```shell
echo "$(ip add | grep -w inet | grep -v 127.0.0.1 | awk NR==1'{print $2}' | cut -d "/" -f 1) $(hostname)" >> /etc/hosts
```

## tomcat

```shell
sed -i -e 's/8080/'$PORT0'/g' -e 's/8009/'$PORT1'/g' -e 's/8005/'$PORT2'/g' conf/server.xml && catalina.sh run
```

**备注**：

1. 将 Tomcat 默认端口替换为`PORT0`、`PORT1`、`PORT2`

```shell
sed -i -e 's/8080/'$PORT0'/g' -e 's/8009/'$PORT1'/g' -e 's/8005/'$PORT2'/g' conf/server.xml
```

2. 启动 Tomcat

```shell
catalina.sh run
```
