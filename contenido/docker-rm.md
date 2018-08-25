---
layout: default
---

# [](#header-1)Eliminar todas las imagenes y contenedores en Docker
***

En esta pequeña publicación deseo hacer un par de apuntes que nos puede ser muy utiles para poder realizar una limpieza en nuestro equipo y así liberar espacio en cuanto a contenedores e imagenes docker se refiere. 

Despues de un largo periodo de tiempo haciendo uso de docker puede ocurrir que prueba tras prueba dejemos acumulados una cantidad bastante importante de imagenes y contenedores en el equipo con el que trabajamos, llegando a consumir la totalidad de la memoria del equipo, acumulando imagenes que ya no son utiles por ser demasiado antiguas (ya que tenemos versiones actualizadas) o incluso por que ya no son necesarias.

Por ello vamos a ver los dos siguientes comandos que nos permite realizar un **BORRADO TOTAL** de todas las imagenes y contenedores que tenemos en nuestro equipo, siendo los dos siguientes comandos.

- **Elimina todos los contenedores docker**
```
docker rm $(docker ps -a -q)
```

- **Elimina todas las imagenes docker**
```
docker rmi $(docker images -q)
```


Si se da el caso que alguno de los contenedores que tenemos que eliminar está iniciado o una de las imagenes tiene dependencias de otras, tendremos que indicarle la opcion (**-f**) que nos permite realizar un borrado forzado y limpiar definitivamente todas las imagenes y contenedores.

Si bien no es un articulo con mucha importancia, pero para uso personal me es muy util para cuando no recuerde el comando correctamente y espero que os sirva para el mismo cometido.

Espero que os sea util. Un saludo.