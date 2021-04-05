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
## Instalacion y Configuracion del SO.
### 
#+BEGIN_NOTE
Se sobreentiende que luego de cada paso es necesario darle a la opcion ^^Done^^ para continuar el proceso de instalacion.
#+END_NOTE
### Bootear el sistema operativo.
### Selección de idioma del instalador.
#### En primera instancia pide el idioma, obviamente seleccionar "**Español**".
##### ![2021_04_05_language.PNG](https://cdn.logseq.com/%2F27628fff-82be-419a-b971-1869717d9bad026b3fda-ad3b-499e-8248-6659fe7366392021_04_05_language.PNG?Expires=4771228572&Signature=UKue7feTjlCfnjOigPicwWibz13RQe7Bg0-HrTBAQp56StsnnUVTGxLMFUcRDdiT9xTayLing0nAK8L4oycf6kEmekojdxSa7e5QPaVHkO8A-78R7uQfAJGt2KPnUb7Vz7V0k589S2tc1S4NhRHgmYCUyyPq9hNtp~Mlznr2uz4~-RM9RLirzDTK4ZhBhfNCUAd-~NI8ceFZZS~lHS5Z2SjB7D5sMKVS0rNcY5ULb12z8sB-5J5Yzr7cIsQTdvsjvRrbpBGgHaJ8caWQlSu2Rqio27TMSxKEUz1aCmv0URqW4BsjWH0L4seIww1qggiJLjrEwoukC7ykG3Ykic6srw__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA){:height 426, :width 560}
### Ejecución instalador de ubuntu 18.04
#### Le damos a la primera opción para comenzar el proceso de instalación.
#### ![2021_04_05_Captura.PNG](https://cdn.logseq.com/%2F27628fff-82be-419a-b971-1869717d9badb1f28987-dc5f-4c51-b789-a0231dbb6f172021_04_05_Captura.PNG?Expires=4771228750&Signature=O5xTRl5TVfL8i1U0I5HPNSrc7A1hEkPN8gdwjBwYdkbr6ktkOphr8DezQl0OB5rLFCFqehLXxWYJwpQpLUwvYjvukmloRmP6meRUhvDHr5eIP1tRcmmM519A-jGAJhsY9Pzau~wEmlh-fLcHyIzEcuuTPrN~TjrDPOHxN0hMAY3QzXsgtPVTHe5eeQySZEA3wy2cHqH8N30lbKVN8o6SSxLnI3yhdg7TAapqem0dMrXESQfitYCO-tf8PEMszYo1jdcwD1kk2V0xDWIe2w0M75LgDk48KCTgTyeKQ9IqsL-QMZRT66VtQRwmr6VaM8q~LWjRI0OWSP~8FE2tgzXIKg__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
### Ubicación, idioma y zona horaria.
#### Seleccionamos una ubicación para que el asistente determine zona horaria y la localización del sistema.
#### ![2021_04_05_Captura.PNG](https://cdn.logseq.com/%2F27628fff-82be-419a-b971-1869717d9badf2bca9bc-86ef-453d-835f-ef03330d20232021_04_05_Captura.PNG?Expires=4771229041&Signature=IVrehq7ILOz5n22VuZZWd2JrDqIxtlg1~aZ1BQXBCEQrm0QOvEmHkZmWcmcg8A1CmQeipa0T3kouoALZjLn33~FAgPkDWW4NMa-z8CoI0~5HrXvI702n1~iLWbe541bx-1IV8djM8B~8E5g-MOG~zrZigDs8zcTGNJHTHq9aruMGH9x-SijCj-8BJiLX8RWLdtrP-tz0xdJtO14cDnRGuUkmCRoZNzwGRDzD0NnwsqdfIVg~p-GaZV7K2ZzeGPMrlKicdVKEhdLSSn18G9Zii1~cfDit6XG4OTbhiOlx2pqiJBQ09LIH4SQlmjA8o7e9MnzXSv7AyPnGGkKh-wDauQ__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
### Selección de la distribución del teclado.
#### La forma mas fácil de determinar el layout del teclado es confirmar la detección del teclado automática que ofrece el instalador. Para lo cual el sistema nos va ir pidiendo ingresar un conjunto de caracteres para seleccionar una distribución. (en este caso es **latam**)
##### TODO Tipear `y` `w` `no` `no` 
:PROPERTIES:
:todo: 1617629136997
:END:
##### ![2021_04_05_Captura.PNG](https://cdn.logseq.com/%2F27628fff-82be-419a-b971-1869717d9badd76c5914-2c8a-4dce-ad00-c5a9073c65462021_04_05_Captura.PNG?Expires=4771229293&Signature=fS-HXXzuC8AUQQeF4agwSe6SMkkcdyaHvtlDkPvwgNDPNr-GCseWD0KE28bEYOVB1aApoosL9Xbs9xnJEfJcIbGZQ4FyzM-sMMbokU83aWGTKKCDditS5hE~I5iUE059tgIcM4b3Ys54zTR-OBzemZbekV4GdYfzbO5kfH23fGlBIRbHEKiUBsDDtaAP5Hjq8~yh-ZmP4huDoqjIRHHdeRDUA8U-goqGmaznBwrBZgB6AKyx3zLvpLFAYqIccg1p-M5vFai7qsr10BNr5dPixMEeQsgh-wQu9xXH4FPPO7lvklUSK4lnVjmr6CmEtOfmNMQ-0BQnqjkiXyZKV6NlHw__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
### Configuración de Red.
#### Ingresamos el hostname, o nombre de la pc.
##### ![2021_04_05_Captura.PNG](https://cdn.logseq.com/%2F27628fff-82be-419a-b971-1869717d9bad33510d74-29ab-4f6b-a1a6-40fa2d10dc0c2021_04_05_Captura.PNG?Expires=4771229639&Signature=houUNK9WBGgaCNomcL0UUjBW-8RBx2enlfrWATiPMA3c7nmZn8YimIP5uO2STK9Wk2RTd4mvD~JA8tCy3DNOGnByWozLfSJE5MUu4u7WGP9UgKbi2bTSjXUo~GqLqKoXOEIhUZ~BalX9kyj~stlhAeS7ok6FNusLiDu9SNbwztIHEfhF5N2jDXaSk5GcMNMnRHdIaGomCSRt-QiznDvvjvl-0KgJRgF1WOmRCBENtFioEJxeMgPmU6mAyrCBWp1D9jWd9JiSs8IfnNNla7f6Sq-IaOo2AuW~AGhrjjO81o3l~pNV4fQ975Pp8~FE7nD7RLz22XgAuEqbPqHCi5HgPw__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
### Creación de cuenta de usuario.
#### Se genera la cuenta de usuario y las credenciales tanto de este usuario como de root. Hay que facilitar al sistema los siguientes datos.
##### Nombre completo. Ej. "Hernan David Jalabert".
##### Nombre de usuario. Ej. "Benabhi".
##### Password.
### Configuracion de servidor proxy.
#### Proxy lo dejamos en blanco o establecemos valor deseado en caso de salir a internet por un proxy.
##### ![2021_04_04_proxy.PNG](https://cdn.logseq.com/%2F27628fff-82be-419a-b971-1869717d9bad33fc5316-1075-4434-81b8-573122fcfeeb2021_04_04_proxy.PNG?Expires=4771159312&Signature=goESOnr7LI6JxtXG8fA7PFqj4Jgu2OZ47lMiJIPTzHWNJ6692RdpuNShyuukpWO2JNdQR49qdJDfW3eGiSZnuy3eVmscE5nsGCGpvYPbMghT~n7JSZgyyuJqRJzRrrhIkg9kUTy0tmunyhOzKE7cUAvkccIAqJ7gq8diqqG0gRH-g~miRksOpPRv6HLq-B2hYq3d4yU-5U-ec5thp9p20bM5zs40aAmfpB3myEZKvJB~hBLo0Nx0cclTXRt7ENWDxRnbg49ABtMeC0E0oi2QnTSzutuVIH2A2aBoncZ-e53oD8-hLr1uWQhHRTyHvQCb-WDEG4vsel~qcIKxrb9Fnw__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
### Direrccion de "Mirrors".
#### Los mirrors lo dejamos como viene por defecto o establecemos el valor deseado en caso de tener una url.
##### ![2021_04_04_mirror.PNG](https://cdn.logseq.com/%2F27628fff-82be-419a-b971-1869717d9bad5272e331-5f3c-475e-841f-b1936cb994a32021_04_04_mirror.PNG?Expires=4771158727&Signature=GUQ68JyEKwHnnAKnSSlUhu08upPuRMQHgSk1DmMsgdhno6unECqPlb2aBR4w~22wrvb7aIFnNhfrWadYVo3aKaPzwWo6YgXkFdrXaOZdQ7PgXvJ1CxgjYL8aOLjfj1LdpAeTHlfHkI1msas~zgqZl8mKd3BJL8To5hK8m8hzVYIqC2Qw-VROhtbksUz-ByfZ-cSCX9fWGo8Z9xGgkDycAeFz4c6RMJRGHJpLdNv-H9aEb3UNFD7PG972WBIQNAQn~CYoY-i1d1gxjt-It9TMJsajL-UAigpWccyd~D3PtQ3lkRGGoNiN877DInXDNq03wXlI~JgGl43kDa3hZSdk0A__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
### Configuracion de discos.
:PROPERTIES:
:background_color: #978626
:END:
#### 
#+BEGIN_NOTE
Esta es la seccion mas gruesa e importante del tutorial, en gran parte este documento es para explicar esta seccion en particular.
#+END_NOTE
#### Seleccion de Layout de los discos.
##### Seleccionamos "**Custom storage layout**".
###### ![2021_04_04_select_disk_layout.PNG](https://cdn.logseq.com/%2F27628fff-82be-419a-b971-1869717d9bad73025c79-55c5-48d6-bf62-52fda30ba0442021_04_04_select_disk_layout.PNG?Expires=4771158135&Signature=SiZTMAHIQiCoZ7b3MYwHM8UEGNXPqt58QT1mM0XBvvghDDaf1wUyFckhsMnol2LLehP4i1VO5X63bTsKRs~VQtBzbkczpu1xeX7fn5lUmsb6GpclQ6z~ghfSKOU4E~H3xHKYtRyjtCfpzZbYndNb7MI2ugrZzu6Tge6vFTHP2fMhi1Qn96z8JTkrCNbj~p3EMEi-HDDjvPczk~XHejijUAc08ToowPzq-jXy05bxw5bYP2vB3zKpohuHHoVYUmkUakd42lFPXORfe6yuiR07vCoKog5j1dJcpyC7SduQTx6e0oE6O0kh6C6ATFoV0Z6Q3a73B23gwjjSREwwaECvyw__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA){:height 410, :width 538}
#### Crear RAID 1.
##### Seleccionamos la opcion "**Create software RAID (md)**".
#### Crear LVM
##### Particion Swap
###### ((606a8bcb-8b8b-4179-913c-5357f781ea6a))
