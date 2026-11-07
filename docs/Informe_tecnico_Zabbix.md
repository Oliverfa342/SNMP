# Informe técnico: Zabbix, DHCP y SNMP

**Estudiante:** Oliver Eliam Aquino Paulino · **Matrícula:** 2024-1571  
**Asignatura:** Seguridad de Redes · **Fecha:** 01/11/2026

## Alcance

Topología en GNS3 con router Cisco R1, switches IOSvL2 SW1/SW2 y Zabbix Appliance 7.0.32 (Rocky Linux 8.10). La red LAN es 10.15.71.0/24.

## Diseño físico

- R1 FastEthernet0/0 ↔ SW1 GigabitEthernet0/0.
- SW1 Gi0/1 ↔ SW2 Gi0/0.
- SW1 Gi0/2 ↔ Zabbix eth0.
- SW1 Gi0/3 ↔ Cloud hacia Windows (VMware VMnet2).

## Direcciones

R1 10.15.71.1/24; SW1 10.15.71.2/24 (Vlan1); SW2 10.15.71.3/24 (Vlan1); Zabbix 10.15.71.100/24 por DHCP.

## DHCP

Pool LAN_ZABBIX, máscara /24 y default-router 10.15.71.1. Rangos excluidos 10.15.71.1–99 y 10.15.71.201–254. En show ip dhcp binding la IP 10.15.71.100 figura como Automatic Active. La IP 10.15.71.104 figura como Selecting y no debe interpretarse como concesión confirmada.

## SNMP

Versión SNMPv2c, puerto UDP/161 y comunidad de solo lectura ZABBIXRO71 en los tres equipos. La localización es LABORATORIO-GNS3 y el contacto Oliver.

## Servidor de monitoreo

Zabbix Appliance 7.0.32 con eth0 dynamic 10.15.71.100/24 y ruta default via 10.15.71.1. Servicios nginx y zabbix-server activos. Hosts R1, SW1, SW2 con la plantilla Network Generic Device by SNMP, dentro del grupo Laboratorio Cisco.

## Evidencias

- Conectividad desde Zabbix hacia los tres equipos Cisco.
- Indicador SNMP verde en R1, SW1, SW2.
- 22 ítems R1, 93 ítems SW1 y 93 ítems SW2 (208 en total).
- ICMP loss 0 %, consultas de tráfico de interfaces y velocidad 100 Mbps en R1 Fa0/0.
- Extractos reales y sanitizados del show running-config de los tres Cisco.

## Limitaciones

No se verificaron alertas, notificaciones, SNMPv3 o monitoreo prolongado. Esta evidencia corresponde exclusivamente a la sesión de laboratorio. Las capturas originales y el informe PDF se adjuntan en el repositorio.
