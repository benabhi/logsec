---
title: Instalar Ubuntu 18.04 con RAID 1 y LVM
---

## 
#+BEGIN_NOTE
Esta guia esta basada en la version 18.04 de ubuntu, puede no ser igual en versiones posteriores.
#+END_NOTE
## Requisitios
### Descargar la imagen de [Ubuntu Server 18.04](https://releases.ubuntu.com/18.04/)
### Crear booteable de la imagen previa (cd, usb, etc)
### Tener al menos dos HDD
## Instalacion y Configuracion del SO
### Bootear el sistema operativo
### En primera instancia pide el idioma, seleccionar "**Español**"
### Es posible que el instalador solicite actualización, seleccionamos "**Actualizar al instalador nuevo**". Esperamos entonces a que finalice la descarga.
### Pasamos a la seleccion de teclado.
#### Establecemos, `Layout` y `Variant` en **Spanish (Latin Amarican)**
#### Done
### En la configuracion de red lo dejamos con esta.
### Proxy lo dejamos en blanco.
### Los mirrors lo dejamos como esta.
### Configuracion de discos.
#### Seleccionamos "**Custom storage layout**"
##### ![2021_04_04_select_disk_layout.PNG](https://cdn.logseq.com/%2F27628fff-82be-419a-b971-1869717d9bad73025c79-55c5-48d6-bf62-52fda30ba0442021_04_04_select_disk_layout.PNG?Expires=4771158135&Signature=SiZTMAHIQiCoZ7b3MYwHM8UEGNXPqt58QT1mM0XBvvghDDaf1wUyFckhsMnol2LLehP4i1VO5X63bTsKRs~VQtBzbkczpu1xeX7fn5lUmsb6GpclQ6z~ghfSKOU4E~H3xHKYtRyjtCfpzZbYndNb7MI2ugrZzu6Tge6vFTHP2fMhi1Qn96z8JTkrCNbj~p3EMEi-HDDjvPczk~XHejijUAc08ToowPzq-jXy05bxw5bYP2vB3zKpohuHHoVYUmkUakd42lFPXORfe6yuiR07vCoKog5j1dJcpyC7SduQTx6e0oE6O0kh6C6ATFoV0Z6Q3a73B23gwjjSREwwaECvyw__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
