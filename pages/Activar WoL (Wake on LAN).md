---
title: Activar WoL (Wake on LAN)
---

## Ver https://www.techrepublic.com/article/how-to-enable-wake-on-lan-in-ubuntu-server-18-04/
## Dependencias
### Para poder realizar las modificaciones es necesario tener instalado ethtool.
### `sudo apt-get install ethtool -y`
## Localizar la interface de red
### Ejecutamos `ip a` para ver el nombre de la interface de red que suele ser **eth0**.
## Configurar WoL
### Creamos un archivo para utilizar systemd `sudo vim /etc/systemd/system/wol.service`.
### Agregamos el siguiente contenido.
#### 
#+BEGIN_SRC 

#+END_SRC