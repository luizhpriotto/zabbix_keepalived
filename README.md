# Keepalived template for Zabbix 6.0

## Install

1) Copy keepalived.addr.discovery.sh and keepalived.addr.availability.sh to /usr/local/bin/.
2) Run chmod +x and test the scripts.
```
./keepalived.addr.discovery.sh /etc/keepalived/keepalived.conf
```
3) Edit  /etc/zabbix/zabbix_agentd.conf.d/keepalived.conf  and put:
```
UserParameter=keepalived.addr.discovery[*],keepalived.addr.discovery.sh $1
UserParameter=keepalived.addr.availability[*],keepalived.addr.availability.sh $1
```
4) Import  **keepalived_template.yaml** in Zabbix.

> **Note:** Tested in Zabbix 6.0 and Debian 11.

Updated from [source](https://github.com/lesovsky/zabbix-extensions/tree/master/files/keepalived).
