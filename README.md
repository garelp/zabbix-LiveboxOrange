# Zabbix template to gather traffic stats from the Livebox.
Since Orange doesn't provide SNMP access to the box, I used upnpc to gather the WAN traffic stats.

## Requirements:
    1. A linux box on the same LAN as the Livebox with the Zabbix Agent. 
    2. the upnpc command installed: 
        On Ubuntu: apt-get install miniupnpc
    3. Check if it works with:
        $ upnpc -s
        You should get status of the Livebox and a line containing:
        Bytes:   Sent: 3898727999       Recv: 3330218288
        Packets: Sent: 347996157        Recv: 776991932

## Usage:
    1. Copy the Zabbix the LiveboxInfo.conf file into /etc/zabbix/zabbix_agentd.d/ on the linux box.
    2. Restart the Zabbix Agent.
    3. Import the template XML file into your zabbix server and add to the correct host.