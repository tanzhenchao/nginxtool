# 工具简介
一款基于Nginx集群的管理工具，支持Nginx集群配置文件检查，服务状态查询、启动、停止、重载、重启、同步

# 安装脚本工具
<pre>
wget -O /usr/bin/nginxtool https://github.com/tanzhenchao/nginxtool/blob/main/nginxtool
chmod +x /usr/bin/nginxtool
</pre>

# 安装脚本配置
<pre>
mkdir /etc/nginxtool/
wget -O /etc/nginxtool/nginxtool.conf https://github.com/tanzhenchao/nginxtool/blob/main/nginxtool.conf
</pre>
另外，如果是docker环境，请换成以下脚本，
<pre>
mkdir /etc/nginxtool/
wget -O /etc/nginxtool/nginxtool.conf https://github.com/tanzhenchao/nginxtool/blob/main/nginxtool-for-docker
</pre>

# 修改脚本配置
<pre>
vim /etc/nginxtool/nginxtool.conf
</pre>
按实际环境修改如下配置，
<pre>
## variable definition

# Define hostnames of all nodes in the cluster
# Please configure name resolution in advance
clusterNode="rproxy01 rproxy02 rproxy03"

# Define the hostname to be configured synchronously
# Please configure name resolution in advance
synNode="rproxy02 rproxy03"

# Define the path or directory of the synchronized configuration file
synConf="/etc/nginx/nginx.conf /etc/nginx/conf.d/ /etc/nginx/public/ /etc/nginx/stream.d/ /etc/nginx/*.crt /etc/nginx/*.key" 
</pre>

# 获取使用帮助
<pre>
nginxtool
</pre>
可见如下显示，
<pre>
Usage: /usr/bin/nginxtool {check|status|start|stop|reload|restart|sync}
</pre>

# 使用范例
<pre>
nginxtool sync
nginxtool check
nginxtool status
nginxtool reload
nginxtool stop
nginxtool start
nginxtool restart
</pre>
