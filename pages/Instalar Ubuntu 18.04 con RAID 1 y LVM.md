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
#### Seleccionar "**Español**" para continuar con el instalador en este idioma.
### Ejecución instalador de Ubuntu 18.04
#### Le damos a la primera opción para comenzar el proceso de instalación.
### Ubicación, idioma y zona horaria.
#### Seleccionamos una ubicación (**Argentina**) para que el asistente determine zona horaria y la localización del sistema.
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
#### Crear el RAID 1 (Array de discos espejados)
##### Terminado lo anterior se habilitan nuevos menus, ir a "**Configurar RAID por software**".
##### Darle a `<Si>` para continuar con el proceso.
##### Seleccionar **"Crear un dispositivo MD"**.
##### Elegir el tipo de RAID, en este caso "**RAID1**"
##### Colocar el numero de dispositivos: "**2**"
##### A continuación se notifica el numero de dispositivos, darle a `<Continuar>`.
##### Seleccionar los dispositivos activos del raid. (Check a los dos discos)
###### 
#+BEGIN_TIP
Usar la barra espaciadora para checkear las casillas.
#+END_TIP
##### Escribir los cambios, `<Si>`.
##### El RAID1 ya esta creado, seleccionar `Terminar` o `<Retroceder>`
#### Configurar LVM (Manejador de volúmenes lógicos).
##### Seleccionar "**Configurar el Gestor de Volúmenes Lógicos**".
##### Mantener la distribución de particiones existentes: `<Si>`.
##### En este menú elegir "**Crear grupo de volúmenes**".
##### En el nombre del grupo de volúmenes seguir el estándar y colocar "**vg0**" y `<Continuar>`.
##### Seleccionar el array de disco (checkbox) /dev/md0 y `<Continuar>`.
##### Mantener la distribución de particiones existentes: `<Si>`.
##### Crear los siguientes volúmenes lógicos en el menú "**Crear un volumen lógico**", seleccionar siempre el unico grupo disponible "**vg0**".
###### **vg-boot**, con 512MB alcanza para esta partición.
###### **vg-swap**, para determinar el tamaño de este volumen ver la siguiente tabla de ayuda: ((606a8bcb-8b8b-4179-913c-5357f781ea6a))
###### **vg-root**, asignar todo el tamaño que quede disponible.
###### `Terminar` o `<Retroceder>` una vez finalizado el proceso.
##### Formatear y montar los recursos
###### 
#+BEGIN_TIP
Para seleccionar los volumenes se utiliza la linea que contiene "**#**" el "**numero del volumen**" y la "**cantidad de espacio**" del mismo, o sea la que sigue a la que tiene el nombre del volumen en cuestion.
#+END_TIP
###### **vg-boot**
####### **Utilizar como**: Sistemas de ficheros ext4 transaccional.
####### **Punto de montaje**: /boot
####### Terminar con `Se ha terminado de definir la partición`.
###### **vg-swap**
####### **Utilizar como**: Área de intercambio.
####### Terminar con `Se ha terminado de definir la partición`.
###### **vg-root**
####### **Utilizar como**: Sistemas de ficheros ext4 transaccional.
####### **Punto de montaje**: /
:PROPERTIES:
:later: 1617635405056
:END:
####### Terminar con `Se ha terminado de definir la partición`.
#### Seleccionar ``Finalizar el particionado y escribir los cambios en el disco`.
#### Confirmar los cambios y escritura `<Si>`.
### Configuración de Proxy.
#### Colocar http://[][usuario]:[contraseña]@]servidor[:puerto] en caso de pasar a través de un proxy.
#### Avanzamos `<Continuar>`.
### Actualizaciones automáticas.
#### 
#+BEGIN_NOTE
En lo personal dejo desactivadas este tipo de automatizaciones que podrían instalar software que provoque comportamientos inesperados en la pc o podrían quitar o actualizar dependencias de otros programas que podrían dejar de funcionar por la actualización. En ultima instancia es mas fácil actualizar el sistema a mano cada vez que se requiera.
#+END_NOTE
#### Seleccionar `Sin actualizaciones automáticas`.
### Selección de programas.
#### El único que es recomendable es "**OpenSSH Server**".
#### Seleccionar las deseadas y `<Continuar>`.
### Terminar la instalación.
#### 
#+BEGIN_WARNING
La maquina se reinicia luego de continuar en este punto.
#+END_WARNING
#### Seleccionar `<Continuar>` para dar cierre al proceso de instalación.
