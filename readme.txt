
修改sudo权限，主要为MegaCli软件获取值赋权，为查看到硬盘状况。
visudo
zabbix  ALL=(ALL)       NOPASSWD: /opt/MegaRAID/MegaCli/MegaCli64
Defaults:zabbix    !requiretty

zabbix_agentd.conf添加或者修改以下参数：
UnsafeUserParameters=1
Timeout=30

zabbix_server.conf添加或者修改以下参数：
Timeout=30

需先安装OMSA组件启动，再安装MegaCli软件包

安装OMSA组件：

基础包安装
yum install libcmpiCppImpl0 libwsman1 sblim-sfcb sblim-sfcc openwsman-client openwsman-server -y
yum源安装
wget -q -O - http://linux.dell.com/repo/hardware/latest/bootstrap.cgi | bash
omsa安装
yum install srvadmin-all -y
bios升级包
yum install dell-system-update -y
启动与停止
/opt/dell/srvadmin/sbin/srvadmin-services.sh start
/opt/dell/srvadmin/sbin/srvadmin-services.sh stop

安装MegaCli软件包
rpm -ivh MegaCli-8.07.10-1.noarch.rpm
