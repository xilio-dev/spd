# 介绍
spd是一个轻量级的通过端口号查询正在运行进程信息的工具，支持精准查找和范围查找，解决Linux原生命令使用繁琐问题。

## 功能特性

- 查看`小于`某个端口的所有进程：`spd port-`
- 查询`大于`某个端口的所有进程: `spd port+`
- `精准`查询某个端口的进程: `spd port`
- 查询某个`范围`的所有进程: `spd port-start port-end`

## 安装教程
将[spd.sh](spd.sh)脚本保存在`/usr/local/bin`目录下，便于直接在控制台调用，下面是mac电脑配置。
```shell
chmod +x spd.sh
sudo mv spd.sh /usr/local/bin/spd
```
上面配置完成以后在命令行终端输入spd可以看到用法案例：
```shell
(base) liuxin@xilio Desktop % spd
Usage: /usr/local/bin/spd <port_range>
Examples:
  /usr/local/bin/spd 8000-    : List processes with ports below 8000
  /usr/local/bin/spd 8000+    : List processes with ports above 8000
  /usr/local/bin/spd 8000-9000: List processes with ports between 8000 and 9000 (inclusive)
  /usr/local/bin/spd 8000     : List processes using port 8000
```
例如查询`8080`端口号对应的进程：
```shell
(base) root@xilio bin % spd 8080
java      5724 root   54u  IPv6 0xd5fe70372f2973db      0t0  TCP *:8080 (LISTEN)
```
