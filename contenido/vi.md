# [](#header-1)Uso de Vi/Vim.
***
El editor vi es un editor de texto de pantalla completa que maneja en memoria el texto entero de un archivo. Es el editor clásico de unix y está en "todas" las versiones de Linux. Puede usarse en cualquier tipo de terminal con un mínimo de teclas, por este motivo surge la fama de que vi es dificil de usar al principio, pero en el momento en el que te acostumbras, tiene infinidad de posibilidades para editar un fichero de la forma mas comoda posible.

En esta publicación vamos a ver como se realiza la edición basica con el editor Vi. Pero, direis...
¿Por que menciona solamente el editor vi y no el vim? Sencillamente menciono en todo momento el editor vi por que el segundo editor que denominado vim no es mas que un editor vi con multitud de extensiones que no facilita la usabilidad de este editor, pero a rasgos generales, el funcionamiento y los comando son los mismo, por ello los comandos que se introducen a continuación servirá para los dos editores.

## [](#header-2)Modos que dispone Vi/Vim.
Dentro del editor de vi/vim exiten diversos modos que nos permiten realizar diversas tareas y tendremos que elegir entre ellas dependiendo de lo que queramos realizar.

<dd> - Modo comando: las teclas nos permite desplazar el cursor por diversas partes del fichero permitiendonos que junto con el realicemos distintas acciones al fichero de cara a la edición.</dd>
<dd> - Modo texto o modo inserción: las teclas ingresan caracteres en el texto del fichero.</dd>
<dd> - Modo última línea: las teclas se usan para escribir comando en la última línea al final de la pantalla.</dd>

## [](#header-2)Uso básico de Vi/Vim.
En este pequeño apartado veremos unos poco comandos básicos que nos permiten sobrevivir a la hora de trabajar con el editor Vi/Vim.

### [](#header-3)Invocación de vi para edición un fichero.
<dd>- Abrir una ventana de edición sin abrir ningún tipo de fichero</dd>

```
vi
```

<dd>- Edición de un fichero denominado fich.txt, si no existe lo creará automaticamente</dd>

```
vi fich.txt
```

<dd>- Editar sucesivamente los fichero fich1.txt y fich2.txt</dd>

```
vi fich1.txt fich2.txt
```

<dd>- Edita el fichero fich.txt posicionado en la línea 16</dd>

```
vi +16 fich.txt
```

<dd>- Edita el fichero fich.txt al final del mismo</dd>

```
vi +$ fich.txt
```

<dd>- Edita el fichero fich.txt en la primera ocurrencia indicada detras del "+/"</dd>

```
vi +/Hola fich.txt
```

### [](#header-3)Inserción de texto en el fichero (parametros a indicar partiendo desde el modo comando).
<dd>- Insertar texto a la izquierda del cursor</dd>
```
i
```
<dd>- Insertar texto a la derecha del cursor</dd>
```
a
```
<dd>- Insertar texto ùna line debajo de la posición actual del cursor</dd>
```
o
```

### [](#header-3)Volver del modo insertar texto al modo comando.
Para volver del modo insertar texto al modo comando, tendremos que pulsar la tecla **ESC**.


### [](#header-3)Desplazarse por el fichero con el cursor.
Para desplazarse por el fichero con el cursos tendremos que realizar el uso de las fechas si la terminal lo permite (**↑↓→←**).

Ademas de las flechas tambien tenemos disponibles para podernos mover con el cursor por el fichero las teclas **h,j,k,l**.

### [](#header-3)Borrado del texto desde el modo comando.
Para poder eliminar líneas de texto desde el modo comando tenemos diversas opciones:
<dd>- Para eliminar el caracter en el que esta el cursor tendremos que introducir la siguiente opción desde el modo comando.</dd>
```
x
```
<dd>- Para eliminar una palabra en la que esté situada el cursos desde el modo comando.</dd>
```
dw
```
<dd>- Para eliminar la fila completa en la que este el cursor situado, tendremos que introducir la siguiente opción desde el modo comando.</dd>
```
dd
```

### [](#header-3)Copiar y pegar.
<dd>- Para copiar una linea tendremos que introducir el siguiente caracter desde el modo comando.</dd>
```
Y ó yy
```
<dd>- Para pegar el contenido que hemos copiado anteriormente tendremos que introducir el siguiente caracter desde el modo comando.</dd>
Antes del cursor
```
P
```
Despues del cursor
```
p
```

### [](#header-3)Realizar busquedas en el fichero.
Para realizar busquedas en el fichero, tendremos que introducir desde el modo comando el caracter **"/"** seguido de la palabra a buscar.

En el momento que lo realicemos, tendremos que pulsar **"n"** para mostrar la siguiente coincidencia y si pulsamos **"N"** mostrar la coincidencia anterior.

### [](#header-3)Comentar un conjunto de líneas.
Para comentar un conjunto de líneas tendremos que realizar los siguiente pasos partiendo desde el principio de las lineas que queramos comentar:
<dd>- Estando en el principio de las lineas a comentar tendremos que entrar en modo bloque visual (VISUAL BLOCK) con "Ctrl+v"</dd>

<dd>- Una vez que hemos entrado en ese modo deslizamos de abajo a arriba para ir seleccionando las lineas a comentar ↑↓</dd>

<dd>- Acto seguido, cuando ya tengamos seleccionadas las lineas deseadas, procederemos a presionar I (i mayúscula) y escribiremos  </dd>
