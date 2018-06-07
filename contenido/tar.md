---
layout: default
---

# [](#header-1)Comprimir y Descomprimir ficheros con tar, zip, .gz y .tar.gz en Linux.
***

En esta publicación vamos a ver de forma breve como vamos a comprimir y descomprimir en los tres formatos mas habituales mediante línea de comandos en Linux con el comando **tar**.

## [](#header-2)Ficheros .tar
#### [](#header-4) - Comprimir
```
tar -cvf fichero.tar /directorio/a/empaquetar
```
#### [](#header-4) - Descomprimir
```
tar -xvf fichero.tar
```

## [](#header-2)Ficheros .zip
#### [](#header-4) - Comprimir
```
zip fichero.zip directorio
```
#### [](#header-4) - Descomprimir
```
unzip fichero.zip
```

## [](#header-2)Ficheros .gz
#### [](#header-4) - Comprimir
```
gzip -9 fichero.txt
```
#### [](#header-4) - Descomprimir
```
gzip -d fichero.txt.gz
```

## [](#header-2)Ficheros .tar.gz
#### [](#header-4) - Comprimir
```
tar -czvf fichero.tar.gz /directorio/a/empaquetar
```
#### [](#header-4) - Descomprimir
```
tar -xzvf fichero.tar.gz
```
