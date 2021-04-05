---
title: Instalar Ubuntu 18.04 con RAID 1 y LVM
---

## [[Apr 4th, 2021]]
## 
#+BEGIN_WARNING
Esta guia esta basada en la version **18.04** de ubuntu, puede no ser igual en versiones posteriores.
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
### Seleccion de idoma.
#### En primera instancia pide el idioma, obviamente seleccionar "**Español**".
##### ![2021_04_04_language.PNG](https://cdn.logseq.com/%2F27628fff-82be-419a-b971-1869717d9bad9237e751-0c35-43ba-af74-eb7304bbb1b22021_04_04_language.PNG?Expires=4771183150&Signature=QSnQGDrgS7NAFetXxOHKfjEe4Z7nCdYvi6Zw-CY0X6ihmsTkZ67BApcIZqkXQwpmTs75vryQo7xOAecNRN2EWfOqMFYttsQ8EagGYyDXHPeb2akWuyarwpmvMeX2Ox7Q24DvbdHv5VyeQ2rq0EJNNJ8oGSSajfV62-feHxtychdtpsUeVjvfmwhZvfKT5cak-Wvoc6TIgptBb6fuCAVNidJShGMpeKcH8UcQ~iaxq1VUxMf-J~xYImdkoiHK442MHRUGu-RjC8xFAfQXejg13d~X323up2ENRVsPcQYipPz1VBPKYPEToSumurfmIPhfR1shLUfJZ72jYJuYVzgIqA__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
### Actualizacion de instalador.
#### Es posible que el instalador solicite actualización, seleccionamos "**Actualizar al instalador nuevo**". Esperamos entonces a que finalice la descarga.
##### ![2021_04_04_update_installer.PNG](https://cdn.logseq.com/%2F27628fff-82be-419a-b971-1869717d9badcce36341-5e68-4b4a-ac51-498bd711e0842021_04_04_update_installer.PNG?Expires=4771183243&Signature=KA57ea~KdqsUoffdfU19IjgIQ1DOi~xKM4xgqzCHJytJR9uNIH5ubr21dfsd9lyPbA6Xd6P6wsyDsettJc1PqTewxQSr0lYfAJWl36tlDbhC1riwLMMwEljsfHHB8kFKOxK6ss-CltvhmO4bAcWwU81~tsuHqWqGJ9IZchceYyn7zexZIPRW~K7s3VlVgMYN6uPxHmk5C~-6TlqntM1uI2xwEtheMcV1b5zYxWzX8JEPO3cGNaElDE~gCZn-MELRVPaL8ncV2trNcqtZEsuZTUV0WTe8Cvk-Ep2v~OplzJzfJmejyWg1xvnQtk5MXFdHltDocP4hTLz0OBmRnkqEJQ__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
### Seleccion de la distribucion del teclado.
#### Establecemos, `Layout` y `Variant` en "**Spanish (Latin Amarican)**".
##### ![2021_04_04_keyboard.PNG](https://cdn.logseq.com/%2F27628fff-82be-419a-b971-1869717d9badff858b2f-e09a-4191-88e0-f55b8ac024442021_04_04_keyboard.PNG?Expires=4771159462&Signature=AfTZLfpgL4AQfOo4cTpGieW4n8VYHKgWDAvidNEyBbSj-DzPnXb~bcg4MuM1stNH48S~YJEaPnojHZGPDjR-RxUX~d~ae5FYtF52xTKYduKREYlxcSYmnhueaxXUpkKEGMe4O69upehl4rIhA8WsB8xmO2fpfaZkqLblrBHSnn0g5qEeiuA2O19VVHUJemhr1CTQvCJ-ci5g92myXveXpZOb6O6D8LfHU-EhJwI-5Z90yqJXA4QvHCHYR6QvOqjrQWR570OO3rGtjtw8Qujp9LllBfx5cRFJbQfcaprd5vaf3Okj3NY40LsLEKg284OuluRQv3NCo0NigxW78biV-w__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
### Configuracion de Red.
#### En la configuracion de red lo dejamos como viene por defecto o configuramos a gusto.
##### ![2021_04_04_network.PNG](https://cdn.logseq.com/%2F27628fff-82be-419a-b971-1869717d9bad5cf31aa6-340c-4548-98f6-f33b7b83c5c22021_04_04_network.PNG?Expires=4771159399&Signature=B1evsEcjT2J1dK7KblB9pOozMK3CDVKP1vTSMkBZEVWmIMZEkmTnNoMP9UUgPfrtDTYYhWPYi5CwQEMmUD93s087UawKinyojkk8u02WL-utYU80QHnDY-N32TlQ9~erGfoi7pk~M032ddiJyARtBtDDuq~26dfqHM~SiuFVWD3Sgh-Yf9kVmv55ZGIFN8QSyaBDMjrqRcwCgRy65UftWE-8zvgczOwA0D4vrDEPMAqVzy~rLKBtNYxBwa~~8h2GazoLP-0dWqEm9EYyPedheEj5XjWgwBwtrDepBQT2cHO4JqnXFF-K4TyLvHfbrJgoEhDlUTwC~UMbU0LoDJQSkg__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
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
