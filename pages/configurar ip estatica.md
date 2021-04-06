---
title: Configurar IP Estatica
---

## Para configurar una IP estatica editar el siguiente archivo  `/hive-config/network/20-ethernet.network`
## Editar los siguientes valores
### **DHCP=no** para evitar dar una ip dinamica.
### **Adress={ IP FIJA / 24 }** esta es la ip que le queremos dar a la pc.
###
## 
#+BEGIN_SRC 
[Match]
#Match eth0, eth1, ... interfaces. Don't change it to other names
Name=e*

[Network]
DHCP=no

#Uncomment the following for static IP, set DHCP=no
Address=192.168.1.100/24
Gateway=192.168.1.1
DNS=192.168.1.1


#to disable IPV6 if it's not disabled in grub
LinkLocalAddressing=no
IPv6AcceptRA=no


[DHCP]
ClientIdentifier=mac
RouteMetric=10

#+END_SRC
