# Configuración

## Switch 1

```bash
enable
configure terminal

vlan 29
name vlan10
exit
vlan 39
name vlan39
exit
vlan 49
name vlan49
exit

interface f1/1
switchport mode access
switchport access vlan 29
no shutdown
exit
interface f1/2
switchport mode access
switchport access vlan 39
no shutdown
exit
interface f1/3
switchport mode access
switchport access vlan 49
no shutdown
exit
do sh vlan-s

interface f1/10
switchport mode trunk
exit
interface f1/11
switchport mode trunk
exit

exit
copy running-config startup-config
```