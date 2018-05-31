---
layout: default
---

# [](#header-1)Uso Básico de GitHub por linea de comandos (Linux/Debian).
***
Para realizar la gestión de los repositorios GitHub mediante linea de comandos para ir gestionando los proyectos que tengamos en nuestro GitHub, tendremos que utilizar el paquete llamado Git, este paquete no se encuentra instalado en el sistema por ello tendremos que instalarlo con el siguiente comando, pero antes de instalar este comando es recomendable actualizar la lista de repositorios del equipo.

## [](#header-2)Cuenta en GitHub.
Para comenzar, antes de instalar ningún paquete, tendremos que tener creado una cuenta en GitHub, y si se da el caso que ya la tienes creada, procederemos a realizar el siguiente paso.

## [](#header-2)Conexión con nuestra cuenta.
Una vez que ya tengamos creada la cuenta, para podernos conectar remotamente a nuestra cuenta en GitHub tendremos que conectarnos con el paquete que vamos a instalar, y ese paquete utiliza una conexión por SSH, por ello tendremos que copiar el contenido de nuestra key publica de SSH (concretamente la "key".pub) y lo tendremos que añadirlo en el apartado de configuración denominado "SSH keys".

En el caso que no tengamos ese fichero con la key creado, lo tendremos que realizar con el siguiente comando.

```
ssh-keygen
```

## [](#header-2)Actualizamos repositorios e instalamos el paquete Git.
Una vez que ya tengamos configurada la key para la conexión ssh a traves del paquete que vamos a intalar, procederemos a realizar la instalación del paquete necesario.

```
apt update
apt install git -y
```

Con estos dos comandos, lo que realizará primero será actualizar la lista de paquetes del sistema y acto seguido instalará el paquete git confirmandolo con la opción **-y**.
 
