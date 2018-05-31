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

## [](#header-2)Clonado de nuestro repositorio de GitHub.
En el momento que ya tengamos instalado el repositorio en nuestro sistema, procederemos a realizar la clonación de un directorio que ya tengamos creado en nuestra cuenta GitHub (en el caso que no lo tengamos, procederemos a crearla para posteriormente clonarla).

Para poder realizar la clonación del repositorio a nuestro equipo, tendremos que copiar la url SSH del repositorio (no copiar la url HTTPS), para ello utilizaremos el siguiente comando.

```
git clone git@github.com:juanjoselopezroldan/github.io.git
```

## [](#header-2)Configuración de git para nuestro repositorio en local clonado.
Una vez que ya tengamos clonado el repositorio, procederemos a configurar nuestra herramienta git para el repositorio que hemos clonado en local y para ello tendremos que introducir los datos de nuestro nombre, nuestro email (email que hace referencia a la cuenta de GitHub) y ademas comprobaremos que de dicho repositorio está correctamente el fichero README.md, ya que en este fichero podemos poner la descripción del repositorio.

```
cd "REPOSITORIO CLONADO"
git config --global user.name "juan jose lopez"
git config --global user.email cuenta_GitHub@gmail.com
git commit --amend --reset-author
```

## [](#header-2)Gestión del repositorio con la herramienta Git.
En el momento que ya tengamos todo los pasos anteriores terminados, procederemos a gestionar nuestro repositorio a traver de la herramienta git.
Esta gestión se realizará a traves de la subida de los cambios realizados en local a nuestro correspondiente repositorio en GitHub gracias a la herramienta git, que consiste en un control de versiones.
A continuación vamos a ver un ejemplo de como se realiza la creación de un fichero y aplicamos ese cambio a nuestro repositorio en la nube.

