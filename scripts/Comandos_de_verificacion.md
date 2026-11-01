# Comandos usados para verificar la práctica

## Router R1 (`R1#`)

~~~cisco
show running-config
show ip interface brief
show ip dhcp binding
show ip dhcp pool
show running-config | include snmp-server
~~~

**Evidencia:** 10.15.71.100 en estado Automatic Active, IP de Fa0/0 10.15.71.1, pool DHCP y SNMP RO.

## Switch SW1 (`SW1#`)

~~~cisco
show running-config
show ip interface brief
show running-config | include snmp-server
ping 10.15.71.1
~~~

**Evidencia:** Vlan1 10.15.71.2/24, puerto Gi0/3 hacia Cloud y comunidad SNMP RO.

## Switch SW2 (`SW2#`)

~~~cisco
show running-config
show ip interface brief
show running-config | include snmp-server
ping 10.15.71.1
~~~

**Evidencia:** Vlan1 10.15.71.3/24 y comunidad SNMP RO.

## Consola de Zabbix (`root@appliance`)

~~~bash
ip link show eth0
ip -4 addr show eth0
ip route
ping -c 4 10.15.71.1
ping -c 4 10.15.71.2
ping -c 4 10.15.71.3
systemctl is-active nginx
systemctl is-active zabbix-server
~~~

## Interfaz de Zabbix

- **Data collection → Hosts:** comprobar los tres hosts y SNMP verde.
- **Monitoring → Latest data:** comprobar tráfico, ICMP y estado de las interfaces.

**Nota:** la comunidad SNMPv2c no está cifrada; el ejemplo corresponde a un entorno aislado.
