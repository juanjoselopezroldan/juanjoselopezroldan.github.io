---
layout: default
---

# [](#header-1)Comprimir y Descomprimir ficheros con tar, zip, .gz y .tar.gz en Linux.
***

En esta publicación vamos a ver de forma breve como vamos a comprimir y descomprimir en los tres formatos mas habituales mediante línea de comandos en Linux con el comando **tar**.

## [](#header-2)Ficheros .tar
### [](#header-3) Comprimir
```
tar -cvf fichero.tar /carpeta/a/empaquetar
```
### [](#header-3) Descomprimir
```
tar -xvf fichero.tar
```

## [](#header-2)Ficheros .zip
### [](#header-3) Comprimir
```
zip fichero.zip
```
### [](#header-3) Descomprimir
```
unzip 
```

## [](#header-2)Ficheros .gz
### [](#header-3) Comprimir
```
gzip -9
```
### [](#header-3) Descomprimir
```
gzip -d
```


## [](#header-2)Ficheros .tar.gz
### [](#header-3) Comprimir
```
tar -czvf
```
### [](#header-3) Descomprimir
```
tar -xzvf
```

