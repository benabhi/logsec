---
title: Activar WoL (Wake on LAN)
---

## Ver https://www.techrepublic.com/article/how-to-enable-wake-on-lan-in-ubuntu-server-18-04/
## Dependencias
### Para poder realizar las modificaciones es necesario tener instalado ethtool.
### `sudo apt-get install ethtool -y`
## Localizar la interface de red
### Eejecutamos `ip a` para ver el nombre de la itnerface de red que suele ser **ethX**  o ****.
