---
layout: default
---

# [](#header-1)Comprimir y Descomprimir ficheros con tar, zip, .gz y .tar.gz en Linux.
***

En esta publicación vamos a ver de forma breve como vamos a comprimir y descomprimir los formatos mas habituales mediante línea de comandos en Linux.

- Ficheros .tar
  - **Comprimir**
```
tar -cvf fichero.tar /directorio/a/empaquetar
```
  - **Descomprimir**
```
tar -xvf fichero.tar
```

- Ficheros .zip
  - **Comprimir**
```
zip fichero.zip directorio
```
  - **Descomprimir**
```
unzip fichero.zip
```

- Ficheros .gz
  - **Comprimir**
```
gzip -9 fichero.txt
```
  - **Descomprimir**
```
gzip -d fichero.txt.gz
```

- Ficheros .tar.gz
  - **Comprimir**
```
tar -czvf fichero.tar.gz /directorio/a/empaquetar
```
  - **Descomprimir**
```
tar -xzvf fichero.tar.gz
```

Además de las opciones que están indicadas en cada caso, podemos incluir diferentes opciones que nos ofrece cada herramienta pero para un uso rapido y estandar, este pequeño manual, resulta muy util.
Espero que os sea util.
