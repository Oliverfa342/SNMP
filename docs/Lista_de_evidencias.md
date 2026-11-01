# Evidencias de Zabbix — relación de capturas

Durante la práctica se obtuvieron las siguientes capturas originales, conservadas en el informe PDF generado y en el paquete ZIP de entrega:

1. **Topología GNS3:** R1, IOSvL2-1 (SW1), IOSvL2-2 (SW2), ZABBIX-SERVER-1 y Cloud1.
2. **Latest data:** tres hosts Cisco con ICMP, latencia, interfaces Fa0/0 y GigabitEthernet, valores de tráfico en bps, velocidad y estado.
3. **Consola Zabbix:** dirección dinámica 10.15.71.100/24, ruta via 10.15.71.1, pings satisfactorios y servicios nginx / zabbix-server activos.
4. **Data collection → Hosts:** Router R1, Switch SW1, Switch SW2; indicadores SNMP verdes, 22 / 93 / 93 ítems.
5. **Router R1:** running-config, show ip dhcp binding (10.15.71.100 Active; 10.15.71.104 Selecting) y show ip interface brief.
6. **SW1 y SW2:** show ip interface brief, comunidad SNMP RO y pings al router.

Los nombres de los archivos digitales originales se han preservado en el paquete de documentación preparado aparte. Esta carpeta identifica las pruebas verificadas **sin afirmar que sus imágenes estén ya alojadas en GitHub**.

**Pendiente de carga al repositorio:** el PDF de 15 páginas y las capturas PNG originales.
