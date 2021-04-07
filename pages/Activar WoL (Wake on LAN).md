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
[Unit]
Description=Configure Wake On LAN

[Service]
Type=oneshot
ExecStart=/sbin/ethtool -s INTERFACE wol g

[Install]
WantedBy=basic.target
#+END_SRC
#### Hacemos que el sistema detecte el nuevo script.
##### `sudo systemctl daemon-reload`
#### Habilitamos el servicio
##### `sudo systemctl enable wol.service`
#### Inicializamos el servicio
##### `sudo systemctl start wol.service`
## Comandos utilies
### Para ver el estado del servicio
#### `sudo systemctl status wol.service`
### Verificar WoL
#### 
#+BEGIN_WARNING
Colocar la itnerface de red que corresponda
#+END_WARNING
#### `ethtool eth0`
#### En wake on lan tiene que esta el valor ^^g^^.
