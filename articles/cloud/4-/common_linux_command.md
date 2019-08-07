# 常用Linux命令

## 查看当前目录

```shell
pwd
```

## 进入某个目录

### 绝对路径

```shell
cd dir_name
```

### 相对路径

绝对路径以`/`开头。

```shell
cd absolute_dir_name
```

## 查看端口

```shell
netstat -anlp
```

## 查找符合条件的字符串

```shell
grep 'match_string' file_name
```

## 查看文件(比如配置文件、日志文件)

### 查看整个文件

```shell
cat file_name
```

**注意：不要使用`cat`命令查看大文件。**

### 查看文件最后1000行

```shell
tail -n 1000 -f file_name
```

> -f: 持续监控文件，如果文件有新的写入，则打印
>
> -n: 行数

配合`grep`，假设要查看包含`ERROR`的字符串：

```shell
tail -n 1000 -f file_name | grep 'match_string'
```

## 查看进程

```shell
ps aux
```

配合`grep`，假设要查看包含`java`的进程：

```shell
ps aux | grep 'java'
```
