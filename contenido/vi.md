# [](#header-1)Uso básico de Vi/Vim.
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

### [](#header-3)Modo visual para seleccionar el texto.
Cuando deseemos marcar/seleccionar un fragmento de texto deseado tendremos que pulsar la tecla **v** estando en la linea de comando y con la ayuda de las fechas iremos moviendo el cursor, marcando así las lineas deseadas.

En el caso que queramos copiar un texto seleccionado para posteriormente pegarlo veremos que opción tendremos que utilizar trabajando de manera conjunta con el modo visual en el siguiente punto.

### [](#header-3)Copiar y pegar.
<dd>- Para copiar un texto tendremos que introducir el siguiente caracter desde el modo comando.</dd>
```
Y
```
<dd>- Para cortar un texto tendremos que introducir el siguiente caracter desde el modo comando:</dd>
```
c
```
<dd>- Para pegar el contenido que hemos copiado anteriormente tendremos que introducir el siguiente caracter desde el modo comando.</dd>
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

<dd>- Acto seguido, cuando ya tengamos seleccionadas las lineas deseadas, procederemos a presionar I (i mayúscula) y escribiremos el caracter que va ha ir en la primera linea que en el caso de bash el comentario sería "#"</dd>

<dd>- En el momento que presionemos el caracter a introducir, solamente se agregará el texto a la línea en la que se ubique el cursor, por ello procederemos a pulsar "ESC" y automaticamente modificará todas las líneas marcadas anteriormente (dependiendo de la versión del editor, pueder esperar unos segundos para ver el cambio o mover el cursos para que se aplique)</dd>

### [](#header-3)Descomentar un conjunto de líneas.
En el caso que queramos descomentar un conjunto de linear tendremos que realizar un proceso similar pero en vez de escribir el caracter, en el momento que tengamos las lineas seleccionadas, tendremos que apretar la letra **d** y borrará todas aquellas lineas que hayan sido marcadas.

### [](#header-3)Reemplazo de texto.
Si se dá el caso que deseamos reemplazar un caracter o texto concreto por otro en todos los puntos que coincida en el fichero tendremos que introducir lo que aparece a continuación desde el modo comando.
```
:%s/cadena a sustituir/cadena nueva/g
```

### [](#header-3)Salir del editor y guardado de datos.
Cuando hayamos terminado de editar el texto deseado tendremos que salir de la edicion del fichero, para salir tenemos diferentes opciones que se describirán a coninuación (estas acciones se realizan desde el modo comando):

<dd>- Si queremos salir de la edición sin haber realizado ningun cambio tendremos que introducir lo siguiente:</dd>
```
:q
```
<dd>- Si queremos salir de la edición pero queremos descartar los cambios que hemos realizado tendremos que introducir lo siguiente:</dd>
```
:q!
```
<dd>- Si queremos guardar los cambio que hemos realizado tendremos que introducir lo siguiente:</dd>
```
:w
```
<dd>- Si queremos salir de la edición guardando los cambios que hemos realizado tendremos que introducir lo siguiente:</dd>
```
:wq
```

Con estos aspectos básicos del editor Vi/Vim podremos defendernos en momentos puntuales o modificaciones básicas, incluso llegando a ser buen punto de comienzo para todo aquel que quiera adentrarse en el mundo de vi.

