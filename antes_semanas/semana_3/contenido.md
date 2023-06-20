# Contenido

Los siguientes contenidos serán presentados en [una sesión de videoconferencia](sesion.md).
Puedes encontrar en [este enlace](slides/slides.pdf) las slides usadas como soporte.

## El superusuario

El usuario más poderoso de un sistema Linux se llama "superusuario" o "root".
Este usuario tiene permisos para modificar y administrar cualquier cosa en el
sistema operativo. Es el usuario que tiene todos los permisos y privilegios
para todo... así que usarás "root" para tareas como interaccionar con los
ficheros del sistema, crear y borrar usuarios, instalar software... Y para
prevenir, declararemos los usuarios comunes sin permiso para realizar estas
tareas.

### sudo

Para acceder a administrar la máquina debemos de hacer uso del "superusuario".
Pero... puede haber usuarios con el poder de ejecutar comandos como si fueran
superusuarios. Son los usuarios con capacidad administrativa. Seguramente si tu
usuario fue el primero en crearse al instalar el sistema, tiene ese superpoder.

Para hacer uso de esa capacidad, hay que ejecutar el comando 'sudo' precediendo
a las órdenes que serán ejecutadas con permisos de superusuario. Veamos un
ejemplo en la siguiente sección sobre cómo instalar software.

## Instalando software

A través de la terminal puedes instalar software. Seguramente ya aprendiste a
hacerlo mediante tu entorno de escritorio, pero puede ser muy útil conocer que
también puedes llevar la gestión de los paquetes de software instalados en tu
computadora a través del terminal.

En este punto, dado que esto sí depende de la distribución de Linux que estés
usando, pondremos aquí los comandos útiles para el caso de Ubuntu y CentOS.

### apt-get

Para actualizar la lista de paquetes disponibles en los repositorios:

```bash
sudo apt-get update
```

Seguramente has tenido que introducir tu contraseña en la terminal. Más
adelante veremos qué significa el comando `sudo`. Ahora, para actualizar los
paquetes que encuentran una versión superior en los repositorios:

```bash
sudo apt-get upgrade
```

Para instalar un paquete:

```bash
sudo apt-get install nombre_paquete
```

La lista de repositorios que tienes configurada en el sistema la puedes
encontrar en el siguiente fichero:

```bash
less /etc/apt/sources.list
```

### yum

Para actualizar la lista de paquetes disponibles en los repositorios:

```bash
yum check-update
```

Para actualizar los paquetes que encuentran una versión superior en los
repositorios:

```bash
yum update
```

Para instalar un paquete:

```bash
yum install nombre_paquete
```

La lista de repositorios que tienes configurado en el sistema la puedes
encontrar en el siguiente directorio:

```bash
ls /yum/yum.repos.d
```

## El sistema de ficheros

En el sistema operativo Linux la organización de archivos tiene forma de arbol.
E independientemente de dónde está físicamente alojado un directorio (puedes
jugar con distintos discos duros) su localización debe estar incluida en esta
estructura anidada que parte de un punto, o directorio supremo, llamado '/' o
directorio raiz. En '/' encontramos el primer nivel de directorios en esta
estructura jerárquica. En este nivel todas las distribuciones suelen tener los
mismos directorios. Vamos a comentar alguno de ellos por orden alfabético:

### /bin

Es la carpeta que almacena los comandos y ejectables, scripts o binarios, del
sistema que usarán todos los usuarios de la máquina. De muchos de ellos
hablaremos en una sección posterior.

### /boot

Es la carpeta que resguarda el gestor de arranque del sistema y sus
instrucciones. El núcleo del sistema ('kernel') va a tener actualizaciones
independientemente de la versión de la distribución de Linux. Cuando enciendes
la computadora, si tienes varios kernels y además algún otro sistema operativo,
aparecerá un menú en el que puedes elegir con qué iniciar la computadora. Eso
es el gestor de arranques, y la información que gestiona está en '/boot'.

### /dev

En Linux cada dispositivo, físico o virtual, o pieza de hardware tiene un
archivo de llamada. Esos archivos están todos en la carpeta '/dev'. Podemos
encontrar allí archivos que hacen referencia a las CPUs, GPUs, USBs, la red,
etc. Usualmente un usuario no administrador no tiene motivo ninguno para operar
con estos ficheros.

### /etc

Puedes encontrar documentación en internet que argumenta que en su origen el
directorio '/etc' almacenaba todos aquellos ficheros que no encontraban su
lugar en cualquier otro directorio contenido en '/'. Puede que de ahí venga su
nombre. Pero hoy en día '/etc' resguarda de manera ordenada la mayoría de
archivos de configuración de software y servicios del sistema.

### /home

Si eres un usuario con poca motivación por convertirte en administrador experto
de tu sistema operativo, esta es tu carpeta. '/home' contiene en su interior un
directorio por usuario. Lo que coloquialmente se conoce como el directorio
hogar o 'home' de cada usuario. Vamos a suponer que tu nombre de usuario es
'chewbacca', encontrarás una carpeta llamada '/home/chewbacca' que será tu
espacio de almacenamiento y trabajo.

### /lib

Aquí encontramos módulos del o los kernels y librerías que en muchas ocasiones
van a ser usadas de manera compartida entre varios procesos, servicios o
programas.

### /media

Como hemos descrito en el párrafo dedicado a '/dev', cada dispositivo viene
anclado a la estructura de ficheros como un archivo o directorio. '/media' es
el directorio que centraliza los puntos de anclaje de los dispositivos
'removibles' como el cdrom, unidades de memoria externas, etc.

### /mnt

Puede haber, comprensiblemente, un poco de confusión entre '/mnt' y '/media'.
Ya que ambos directorios alojan archivos de anclaje de periféricos, pero '/mnt'
suele ser para dispositivos temporales y de usuarios específicos. Aunque esta
regla no siempre se cumple.

### /opt

Es el lugar de almacenamiento del software instalado ajeno al sistema y de uso
para todos los usuarios.

### /proc

No sólo los dispositivos físicos tienen un punto de anclaje, también los
virtuales y los procesos mismos. '/proc' almacena archivos de información del
sistema y una larga lista de directorios etiquetadas por números: PIDs. El PID
es el número de identificación de proceso. Cualquier cosa que se ejecuta en la
computadora se registra como un proceso con un PID. Esas carpetas por lo tanto
tienen en su interior todo la información relacionada con la ejecución de cada
proceso. 

### /root

Directorio "home" para el superusuario 'root'. Más adelante se dedica una
sección al superusuario 'root'.

### /sbin

Este directorio es similar a '/bin'. Es último almacena comandos útiles para
todo usuario, mientras que en 'sbin' podemos encontrar los ejecutables
(comandos) de administración y gestión del sistema.

### /sys

Aquí podemos encontrar toda la información relacionada con el hardware y los
módulos de los kernel instalados.

### /tmp

Este directorio sirve de archivo temporal para ficheros. Su contenido es
borrado cada vez que se reinicia el sistema.

### /usr

Este directorio es seguramente el más poblado en número de ficheros. '/usr'
contiene una estructura similar a la que tiene '/', y sirve para almacenar de
manera organizada las partes de los paquetes y software instalados por los
usuarios, no por el administrador ni por el mismo sistema.

### /var

Contiene ficheros auxiliares del sistema, usualmente 'logfiles' que reportan la
salida en tiempo real de muchos de los servicios del sistema como impresión,
mail interno, procesos internos, etc.

Como ves no es que Linux tenga 'una' carpeta que se llame 'sistema'. Más bien
hay una carpeta que alberga todo el espacio de almacenamiento privado de cada
usuario ('/home') y el resto es una estructura de archivos optimizada para
asegurar el funcionamiento del sistema operativo a varios usuarios ejecutando
varios procesos simultaneamente.

## La navegación por el sistema de ficheros

La terminal es una herramienta poderosísima. Todo lo que necesitas hacer con la
computadora se puede hacer a través de la terminal, no requieres el entorno
gráfico para nada. Y la navegación de ficheros es probablemente lo menos
relevante pero lo más sencillo de entender para comenzar a sentirte cómodo o
cómoda con la terminal.

Como decíamos en la sección anterior, el sistema de archivos tiene estructura
de árbol y podemos escribir la secuencia de directorios que contienen, como
muñecas rusas, el fichero con el que queremos trabajar. A esta dirección, o
secuencia de directorios, se le llama camino o 'path'. Si el 'path' comienza en
el directorio raiz, se dice que el *path* absoluto. Si sin embargo se trata del
recorrido que tenemos que hacer desde el directorio en el que se encuentra la
terminal u otro directorio, se dice *path* relativo -efectivamente path es una
palabra tan comunmente usada en este contexto hemos dejado de
entre-comillarla-.

Vamos a hacer una serie de ejercicios que nos ayuden a introducir la navegación
de ficheros, su sintaxis y los comandos más útiles. Comencemos abriendo una
terminal. Para esto suele funcionar las primeras veces acudir al menú de
aplicaciones de tu entorno de escritorio, aunque poco a poco sentirás la
necesidad de usar una combinación de teclas que rápidamente, sin mover la mano
al ratón, te dispare terminales nuevas. En el caso de Gnome y Ubuntu, esta es
'ctrl'+'alt'+'t'.

### pwd, ls y cd

En este momento tienes una terminal expectante a tus ordenes. Ves tu nombre de
usuario, el nombre de tu máquina, y no me equivocaré mucho si predigo que estás
viendo el símbolo '\~' entre ':' y '\\$'. Ese simbolo, llamado virgulilla, se
usa como álias de tu 'home'. Es decir, si tu usuario, cómo decíamos
anteriormente, se llama 'chewbacca', '\~' es lo mismo que '/home/chewbacca'. Y
el espacio en el 'prompt' entre ':' y '\\$' está dedicado a contener el path
del directorio en el que se encuentra la terminal. Si de todas formas te
desorientas, o tu prompt no es lo suficientemente explícito, existe un comando
que imprime en la terminal el path en el que te encuentras: `pwd` (del inglés
*print working directory*). Ejecútalo y comprueba la relación entre '\~' y tu
'home':

```bash
pwd
```

Para listar el contenido de un directorio disponemos del comando `ls`.
Ejecútalo para ver los ficheros y directorios que se encuentran en tu home.

```bash
ls
```

Ya conoces tus dos primeros comandos. Si has leido la sección previa llamada
[*La organización de ficheros del sistema Linux*](#organizacion), puede que
estés pensando: ¿Estos son comandos que se encuentran en algún sitio? Si, en
'/bin'. A ver si los encuentras allí:

```bash
ls /bin
```

Puedes ahora ver el contenido de tu directorio raíz:

```bash
ls /
```

O de nuevo, pero de otra forma, el contenido de tu directorio hogar:

```bash
ls ~
```

Ahora veamos como cambiar de directorio. El comando `cd` (del inglés *change
directory*) ubica la terminal en el directorio que le digamos. Por ejemplo,
podemos movernos al directorio raíz '/' y descubrir los directorios que hay en
él y que se han relatado en la sección [*La organización de ficheros del
sistema Linux*](#organizacion):

```bash
cd /
ls
```

También `cd` tiene ciertos atajos. Por ejemplo, `cd` solito te lleva a tu
directorio hogar:

```bash
cd /bin
pwd
cd
pwd
```

Ahora imaginemos que existe un directorio llamado 'dir4' ubicado en el
directorio 'dir3', que a su vez está ubicado en 'dir2', ubicado en 'dir1',
contenido en el directorio raíz '/'. Se dice que su path absoluto es
'/dir1/dir2/dir3/dir4', ya que desde cualquier ubicación `cd
/dir1/dir2/dir3/dir4` nos lleva a 'dir4'. Vamos a hacer un ensayo, y para ello
vamos a crear en tu directorio hogar la carpeta 'dir3' y dentro de ella 'dir4'.

```bash
cd # puedes hacer después `pwd` comprobar dónde estás
mkdir dir3
cd dir3 # puedes hacer después `pwd` comprobar dónde estás
mkdir dir4
cd dir4 # puedes hacer después `pwd` comprobar dónde estás
```

Hemos visto, de paso, que `mkdir` sirve para crear directorios. Vamos ahora a
cambiar nuestra ubicación en la terminal a un directorio cualquiera como puede
ser `/usr` para después regresar, haciendo uso de su path absoluto, a `dir4`.

```bash
cd /usr
pwd
cd /home/diego/dir3/dir4
pwd
```

Ahora que ya sabemos lo que es el path absoluto, veamos cómo nos podemos mover
en el árbol de ficheros con paths relativos. Anteriormente hemos visto como
subir un fichero en la jerarquía de la estructura. Si estamos por ejemplo en
nuestro 'home' basta con mencionar uno de los directorios que contiene para
entrar en el:

```bash
cd ~ # o sólamente cd
pwd
cd dir3
pwd
cd dir4
```

¿Y cómo retrocedemos? ¿Cómo descendemos en la estructura de ficheros hasta
llegar a la raíz '/'? Supongamos que estamos en 'dir4', usamos `..` para
descender un nivel -al directorio anterior-:

```bash
cd ~/dir3/dir4
pwd
cd ..
pwd
cd ..
pwd
cd ..
pwd
```

Puedes usarlo también de manera combinada para descender más de un nivel:

```bash
cd ~/dir3/dir4
pwd
cd ../..
pwd

cd ~/dir3/dir4
cd ../../..
pwd
```

Puedes también construir paths que indican una ruta de cambio de directorio
según el punto en el que estés, paths relativos:

```bash
cd ~/dir3/dir4
pwd
cd ../../../../usr/local
pwd
cd ../../bin
pwd
cd ../home/diego/../diego/../diego/dir3/../../diego/dir3/dir4
pwd
```

Por último, y para completar la sintaxis que debes conocer para moverte en el
sistema de ficheros, así como `..` quiere decir *el directorio anterior*, `.`
quiere decir *aquí*:

```bash
cd
pwd
cd .
pwd
cd dir3/dir4/.
pwd
```

## Creando, moviendo y borrando

### mkdir, touch, mv, rm y rmdir

Como vimos en la sección anterior, podemos crear directorios con `mkdir`:

```bash
mkdir dir3
cd dir3 # puedes hacer después `pwd` comprobar dónde estás
mkdir dir4
```

Para borrar un directorio vacío podemos hacer uso del comando `rmdir`:

```bash
cd ~/dir3/.
rmdir dir4
cd ..
rmdir dir3
pwd
```

Has borrado los directorios `dir3` y `dir4`. Vamos a probar ahora crearlos de
nuevo, pero esta vez los dos uno dentro del otro de una sóla vez:

```bash
mkdir -p dir3/dir4
```

Para borrar un fichero o directorio hacemos uso del comando `rm`. Debemos
añadirle `-r` para hacer un borrado recursivo para borrar un directorio y todo
su contenido:

```bash
rm -r dir3
```

Ahora, para crear ficheros -vacíos- podemos usar el comando `touch`:

```bash
cd
ls
touch foo1
touch foo2
touch foo3
ls
```

Usamos ahora `rm` para borrar los ficheros. Recuerda que `rmdir` borra únicamente directorios vacios.

```bash
cd
ls
rm foo1 foo2 foo3
ls
```

Para renombrar o mover un fichero o directorio contamos con el comando `mv` (del inglés *move*):

```bash
cd
ls
mkdir zaragoza79
touch zaragoza79/foo
ls zaragoza79
mv zaragoza79 méxico16
ls méxico16
mv méxico16/foo .
ls
ls méxico16
rmdir méxico16
rm foo
```

Nota que para borrar el directorio 'méxico16' no hemos hecho uso del comando
'rmdir', ya que únicamente funciona con directorios vacíos. Para borrar
`méxico16` hacemos un borrado recursivo con `rm -r`. `-r` otorga efecto sobre
el directorio y todo su contenido.

Para terminar con la navegación de ficheros, veamos ciertos caracteres comodín
(en inglés *wildcard*) muy utiles para hacer la gestión de ficheros más cómoda.
Veamos si puedes deducir para qué podemos emplear el carácter `?` y el carácter
`*` introducido en un path:

```bash
cd
ls
mkdir dir10 dir20 dir30 dir01 dir02 dir03
ls
rmdir dir?0
ls
rmdir dir0?
ls
```


```bash
cd
ls
touch x1xpatatas x1xpatos x1xpatotas x1xpatitos
ls
rm x1xpat?tas
ls
rm x1xp*
ls
touch x1xpatatas x1xpatos x1xpatotas x1xpatitos
rm x1xpat?t*
ls x1x*
rm x1x*
```

Tienes más ejemplos del uso de los comodines en internet en páginas como
[esta](https://kompjuteras.com/en/wildcards-in-linux-commands-with-practical-examples/)
o [esta](https://www.tecmint.com/use-wildcards-to-match-filenames-in-linux/).

## Imprimiendo texto

### echo

Antes de ver en acción dos comandos muy útiles para visualizar el contenido de
un fichero, veamos que hace el comando `echo`. `echo` imprime por pantalla el
texto que pongamos a continuación:

```bash
echo "hola!"
```

A la salida por terminal se llama `stdout` (del inglés *standard output*).
Podemos redirigir la salida por `stdout` del comando a un fichero con el
carácter `>`:

``` bash
echo "hola!" > mi_nuevo_fichero
```

## Viendo el contenido de los ficheros

### more y less

Ahora, para visualizar el contenido del fichero, es donde aparecen los comandos
`less` o `more`. Los dos sirven para lo mismo aunque `less` se inventó más
tarde superando en funcionalidad a `more`. Es por eso que se llamó `less`, por
el dicho inglés: *less is more*.

``` bash
more mi_nuevo_fichero
```

```bash
less mi_nuevo_fichero
# Presiona la tecla 'q' para volver a la terminal
``` 

Pero el desvío de `stdout` a un fichero mediante `>` tiene una peculiaridad, siempre reescribe el fichero:

```bash
echo "Hola Ana" > mi_nuevo_fichero
more mi_nuevo_fichero

echo "Hola Bastian" > mi_nuevo_fichero
more mi_nuevo_fichero

echo "Hola Kitzia" > mi_nuevo_fichero
more mi_nuevo_fichero

echo "Hola Emiliano" > mi_nuevo_fichero
more mi_nuevo_fichero
```

Si quieres que las entradas vayan registrandose en el fichero de manera concatenada, has de usar `>>`:

```bash
echo "Hola Ana" > mi_nuevo_fichero
echo "Hola Bastian" >> mi_nuevo_fichero
echo "Hola Kitzia" >> mi_nuevo_fichero
echo "Hola Emiliano" >> mi_nuevo_fichero
more mi_nuevo_fichero
```

Una última cosa, si `more` saca por pantalla el contenido de un fichero, ¿podemos desviar su salida estandard a otro fichero?

```bash
more mi_nuevo_fichero > otro_fichero
more otro_fichero
```

## Concatenando y uniendo ficheros

### cat y paste

Hagamos ahora un fichero con una columna de números y otro fichero con una columna de letras:

```bash
echo "1" > fichero_numeros
echo "2" >> fichero_numeros
echo "3" >> fichero_numeros
echo "4" >> fichero_numeros
more fichero_numeros
```

```bash
echo "a" > fichero_letras
echo "b" >> fichero_letras
echo "c" >> fichero_letras
echo "d" >> fichero_letras
more fichero_letras
```

Dejaré ahora que adivines el efecto de los comandos `cat` y `paste` cuando se aplican sobre más de un fichero:

```bash
cat fichero_numeros fichero_letras
```

```bash
paste fichero_numeros fichero_letras
```

O volcando la salida a un fichero:

```bash
cat fichero_numeros fichero_letras > nuevo_fichero
more nuevo_fichero
```

```bash
paste fichero_numeros fichero_letras > nuevo_fichero
more nuevo_fichero
```

## Mi primer filtrado de texto

### grep

Algo que harás habitualmente es el filtrado y reconocimiento de texto
directamente desde la línea de comandos. Vamos a presentar en esta sección tres
herramientas que pueden serte de utilidad. La primera, `grep`, filtra de manera
muy sencilla líneas según contengan o no el patrón que estás buscando. Un
ejemplo:

```bash
echo "Paso 0   Energía 10.4" > Experimento_626.oup
echo "Paso 0   Temperatura 303" >> Experimento_626.oup
echo "Paso 1   Energía 10.2" >> Experimento_626.oup
echo "Paso 1   Temperatura 300" >> Experimento_626.oup
echo "Paso 2   Energía 10.5" >> Experimento_626.oup
echo "Paso 2   Temperatura 306" >> Experimento_626.oup
echo "Paso 3   Energía 10.1" >> Experimento_626.oup
echo "Paso 3   Temperatura 299" >> Experimento_626.oup
echo "Paso 4   Energía 10.8" >> Experimento_626.oup
echo "Paso 4   Temperatura 302" >> Experimento_626.oup
echo "Paso 5   Energía 10.1" >> Experimento_626.oup
echo "Paso 6   Temperatura 304" >> Experimento_626.oup
```

Podemos fácilmente filtrar las líneas que contienen o no la palabra *Temperatura*:

```bash
grep 'Temperatura' Experimento_626.oup > Temperatura_Experimento_626.oup
grep -v 'Temperatura' Experimento_626.oup > Energía_Experimento_626.oup
```

```bash
more Temperatura_Experimento_626.oup
more Energía_Experimento_626.oup
```

En la terminal de Linux la salida de un comando se puede redireccionar como la
entrada de otro comando. Por ejemplo, podemos filtrar `stdout` como si de un
fichero se tratara:

```bash
less Energía_Experimento_626.oup | grep '10.1' > Energía_10.1_Experimento_626.oup
```

De hecho, es lo que hacemos cuando escribimos la salida de la línea anterior a
un fichero, porque lo podríamos dejar únicamente como:

```bash
less Energía_Experimento_626.oup | grep '10.1'
```

Así por ejemplo podemos concatenar filtros:

```bash
less Experimento_626.oup | grep 'Energía' | grep '10.1'
```

## Mi primer script

### Hola mundo!

A la terminal le podemos ofrecer ordenes de manera interactiva y secuencial, o
podemos escribir esa lista de ordenes en un fichero y pedirle que las ejecute
como un programa, línea a línea. Eso es un script: un fichero de texto plano
que codifica secuencialmente la lista de ordenes que queremos ejecutar y que se
ejecutan mediante la participación de un interpretador del fichero. En este
caso el interpretador de Bash. Que dónde está ese interpretador:

```bash
which bash
``` 

Hagamos un ejemplos sencillo:

```bash
echo `echo "Hola mundo!"` > hola_mundo.sh
```

Ahora prueba a decirle a tu computadora que procese ese fichero con
el interpretador `bash`:

```bash
bash hola_mundo.sh
```

Veremos en las semanas posteriores como hacer scripts mucho más complejos que
este, cómo declarar el script ejecutable, y como declararlo como "comando" que
puede ser ejecutado en la terminal desde cualquier sitio. Pero eso será más
adelante, por ahora: ¡enhorabuena!, has escrito tu primer script.

