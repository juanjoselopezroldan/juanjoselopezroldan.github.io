---
layout: default
---

# [](#header-1)Comprimir y Descomprimir ficheros con tar, zip, .gz y .tar.gz en Linux.
***

En esta publicación vamos a ver de forma breve como vamos a comprimir y descomprimir los formatos mas habituales mediante línea de comandos en Linux.

## [](#header-2)Ficheros .tar
### [](#header-3) - Comprimir
```
tar -cvf fichero.tar /directorio/a/empaquetar
```
### [](#header-3) - Descomprimir
```
tar -xvf fichero.tar
```

## [](#header-2)Ficheros .zip
### [](#header-3) - Comprimir
```
zip fichero.zip directorio
```
### [](#header-3) - Descomprimir
```
unzip fichero.zip
```

## [](#header-2)Ficheros .gz
### [](#header-3) - Comprimir
```
gzip -9 fichero.txt
```
### [](#header-3) - Descomprimir
```
gzip -d fichero.txt.gz
```

## [](#header-2)Ficheros .tar.gz
### [](#header-3) - Comprimir
```
tar -czvf fichero.tar.gz /directorio/a/empaquetar
```
### [](#header-3) - Descomprimir
```
tar -xzvf fichero.tar.gz
```

Además de las opciones que están indicadas en cada caso, podemos incluir diferentes opciones que nos ofrece cada herramienta pero para un uso rapido y estandar, este pequeño manual, resulta muy util.
Espero que os sea util.
