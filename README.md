# MTProxy TLS 绿色版一键安装脚本

## 安装

执行如下代码进行安装

```bash
## 新建目录
mkdir /home/mtproxy && cd /home/mtproxy

## 开始安装
curl -s -o mtproxy.sh https://raw.githubusercontent.com/sunpma/mtp/master/mtproxy.sh && chmod +x mtproxy.sh && bash mtproxy.sh
```

 ![demo.png](https://raw.githubusercontent.com/sunpma/mtp/master/demo.png)

## 使用

运行服务

```bash
bash mtproxy.sh start
```
调试运行

```bash
bash mtproxy.sh debug
```

停止服务

```bash
bash mtproxy.sh stop
```

重启服务

```bash
bash mtproxy.sh restart
```



## 卸载安装

因为是绿色版卸载极其简单，直接删除所在目录即可。

```bash
rm -rf /home/mtproxy
```

## 开机启动

```bash
chmod 755 /home/mtproxy/mtproxy.sh

vi /etc/crontab

## 在最后加入此行后保存即可；
@reboot root nohup bash /home/mtproxy/mtproxy.sh start > /dev/null 2>&1 &
```
