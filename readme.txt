
�޸�sudoȨ�ޣ���ҪΪMegaCli�����ȡֵ��Ȩ��Ϊ�鿴��Ӳ��״����
visudo
zabbix  ALL=(ALL)       NOPASSWD: /opt/MegaRAID/MegaCli/MegaCli64
Defaults:zabbix    !requiretty

zabbix_agentd.conf��ӻ����޸����²�����
UnsafeUserParameters=1
Timeout=30

zabbix_server.conf��ӻ����޸����²�����
Timeout=30

���Ȱ�װOMSA����������ٰ�װMegaCli�����

��װOMSA�����

��������װ
yum install libcmpiCppImpl0 libwsman1 sblim-sfcb sblim-sfcc openwsman-client openwsman-server -y
yumԴ��װ
wget -q -O - http://linux.dell.com/repo/hardware/latest/bootstrap.cgi | bash
omsa��װ
yum install srvadmin-all -y
bios������
yum install dell-system-update -y
������ֹͣ
/opt/dell/srvadmin/sbin/srvadmin-services.sh start
/opt/dell/srvadmin/sbin/srvadmin-services.sh stop

��װMegaCli�����
rpm -ivh MegaCli-8.07.10-1.noarch.rpm
