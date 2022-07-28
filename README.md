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

## 加入下面这条命令后保存即可；

@reboot root nohup bash /home/mtproxy/mtproxy.sh start > /dev/null 2>&1 &
```

## 服务器设置

如果启动后如果无法访问，请检查一下服务器的端口是否打开了
以下以centos7 为例
```bash
firewall-cmd --zone=public --add-port={your_port}/tcp --permanet
systemctl restart firewalld.service
firewalld-cmd --list-ports
```