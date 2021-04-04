---
title: Instalar Ubuntu 18.04 con RAID 1 y LVM
---

## [[Apr 4th, 2021]]
## /
## 
#+BEGIN_WARNING
Esta guia esta basada en la version **18.04** de ubuntu, puede no ser igual en versiones posteriores.
#+END_WARNING
## Requisitios
### Descargar la imagen de [Ubuntu Server 18.04](https://releases.ubuntu.com/18.04/)
### Crear booteable de la imagen previa (cd, usb, etc)
### Tener al menos dos HDD
## Instalacion y Configuracion del SO
### 
#+BEGIN_NOTE
Se sobreentiende que luego de cada paso es necesario darle a la opcion ^^Done^^ para continuar el proceso de instalacion.
#+END_NOTE
### Bootear el sistema operativo
### Seleccion de idoma
#### En primera instancia pide el idioma, obviamente seleccionar "**Español**"
### Actualizacion de instalador.
#### Es posible que el instalador solicite actualización, seleccionamos "**Actualizar al instalador nuevo**". Esperamos entonces a que finalice la descarga.
### Seleccion de la distribucion del teclado.
#### Establecemos, `Layout` y `Variant` en "**Spanish (Latin Amarican)**"
### Configuracion de Red.
#### En la configuracion de red lo dejamos como viene por defecto o configuramos a gusto.
### Configuracion de servidor proxy.
#### Proxy lo dejamos en blanco o establecemos valor deseado en caso de salir a internet por un proxy.
### Direrccion de "Mirrors".
#### Los mirrors lo dejamos como viene por defecto o establecemos el valor deseado en caso de tener una url.
##### ![2021_04_04_mirror.PNG](https://cdn.logseq.com/%2F27628fff-82be-419a-b971-1869717d9bad5272e331-5f3c-475e-841f-b1936cb994a32021_04_04_mirror.PNG?Expires=4771158727&Signature=GUQ68JyEKwHnnAKnSSlUhu08upPuRMQHgSk1DmMsgdhno6unECqPlb2aBR4w~22wrvb7aIFnNhfrWadYVo3aKaPzwWo6YgXkFdrXaOZdQ7PgXvJ1CxgjYL8aOLjfj1LdpAeTHlfHkI1msas~zgqZl8mKd3BJL8To5hK8m8hzVYIqC2Qw-VROhtbksUz-ByfZ-cSCX9fWGo8Z9xGgkDycAeFz4c6RMJRGHJpLdNv-H9aEb3UNFD7PG972WBIQNAQn~CYoY-i1d1gxjt-It9TMJsajL-UAigpWccyd~D3PtQ3lkRGGoNiN877DInXDNq03wXlI~JgGl43kDa3hZSdk0A__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
### Configuracion de discos.
:PROPERTIES:
:background_color: #978626
:END:
#### Esta es la seccion mas gruesa e importante del tutorial.
#### Seleccionamos "**Custom storage layout**"
##### ![2021_04_04_select_disk_layout.PNG](https://cdn.logseq.com/%2F27628fff-82be-419a-b971-1869717d9bad73025c79-55c5-48d6-bf62-52fda30ba0442021_04_04_select_disk_layout.PNG?Expires=4771158135&Signature=SiZTMAHIQiCoZ7b3MYwHM8UEGNXPqt58QT1mM0XBvvghDDaf1wUyFckhsMnol2LLehP4i1VO5X63bTsKRs~VQtBzbkczpu1xeX7fn5lUmsb6GpclQ6z~ghfSKOU4E~H3xHKYtRyjtCfpzZbYndNb7MI2ugrZzu6Tge6vFTHP2fMhi1Qn96z8JTkrCNbj~p3EMEi-HDDjvPczk~XHejijUAc08ToowPzq-jXy05bxw5bYP2vB3zKpohuHHoVYUmkUakd42lFPXORfe6yuiR07vCoKog5j1dJcpyC7SduQTx6e0oE6O0kh6C6ATFoV0Z6Q3a73B23gwjjSREwwaECvyw__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
