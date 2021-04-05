---
title: Instalar Ubuntu 18.04 con RAID 1 y LVM
---

## [[Apr 4th, 2021]]
## 
:PROPERTIES:
:id: 606b0479-5b1c-4af6-8a5f-a9aab811280b
:END:
#+BEGIN_WARNING
Esta guiá esta basada en la versión **18.04** de ubuntu, puede no ser igual en versiones posteriores. ^^Es necesario utilizar la imagen que tiene el instalador "alternativo" de nombre **ubuntu-18.04-server-amd64.iso**^^ (asegurarse que no tenga "live" en el nombre) se puede descargar desde [Este enlace]( http://old-releases.ubuntu.com/releases/bionic/). Esto ultimo es por que con el nuevo instalador hay un problema para crear la partición de arranque /boot en un array de discos espejado (RAID 1).
#+END_WARNING
## Requisitios
### Descargar la imagen de [Ubuntu Server 18.04](https://releases.ubuntu.com/18.04/).
### Crear booteable de la imagen previa (cd, usb, etc).
### Tener al menos dos HDD.
## Instalación y Configuración del SO.
### Bootear el sistema operativo.
### Selección de idioma del instalador.
#### En primera instancia pide el idioma, obviamente seleccionar "**Español**".
### Ejecución instalador de Ubuntu 18.04
#### Le damos a la primera opción para comenzar el proceso de instalación.
### Ubicación, idioma y zona horaria.
#### Seleccionamos una ubicación para que el asistente determine zona horaria y la localización del sistema.
### Selección de la distribución del teclado.
#### La forma mas fácil de determinar el layout del teclado es confirmar la detección del teclado automática que ofrece el instalador. Para lo cual el sistema nos va ir pidiendo ingresar un conjunto de caracteres para seleccionar una distribución. (en este caso es **latam**)
##### TODO Tipear `y` `w` `no` `no`
:PROPERTIES:
:todo: 1617629136997
:END:
### Configuración de Red.
#### Ingresamos el hostname, o nombre de la pc que sera lo que identificara el ordenador a travez de lar red.
### Creación de cuenta de usuario y contraseñas.
#### 
#+BEGIN_TIP
Ver el numlock por lo general siempre esta desactivado -.-#
#+END_TIP
#### Se genera la cuenta de usuario y las credenciales tanto de este usuario como de root. Hay que facilitar al sistema los siguientes datos.
##### Nombre completo. Ej. "Hernan David Jalabert".
##### Nombre de usuario. Ej. "Benabhi".
##### Password (y confirmación del mismo).
### Particionado de Discos
#### Seleccionar el particionado de disco "**Manual**".
#### En el siguiente Darle `enter` a cada uno de los discos y generar su correspondiente tabla de particiones.
#### Terminado lo anterior se habilitan nuevos menus, ir a "**Configurar RAID por software**".
##### Darle a **<si>**
####
