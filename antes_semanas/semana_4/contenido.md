# Contenido

Los siguientes contenidos serán presentados en [una sesión de videoconferencia](sesion.md).
Puedes encontrar en [este enlace](slides/slides.pdf) las slides usadas como soporte.

## Los procesos en Linux

### top, ps y kill. <a class="anchor" id="top"></a>

Anteriormente, a propósito del directorio `/proc` dijimos que todo proceso ejecutado por la computadora lleva asociado un número como identificador, el PID. El comando `top` nos lista los procesos regitrados activos, durmientes o suspendidos:

```bash
top
```

El mismo `top` nos permite por ejemplo "matar" un proceso que se ha podido
quedar colgado o está dando problemas. O sencillamente queremos abortarlo por
algún motivo. Veremos esto más adelante, en esta sección. Vamos a configurar
una sencilla situación de ejemplo para ilustrar esto.

Anteriormente hemos visto que `more` saca todo el contenido del fichero en la
terminal, pero a veces el fichero es excesivamente largo. Si lo visualizas con
`more` todas las líneas aparecerán en tu terminal, haciendo muy incomodo que
quieras regresar en ella a ver tu historial de comandos. Para poder navegar
mejor en la visualización del fichero, porque *less is more* -un dicho inglés-,
`less` nos permite ir adelante y hacia atrás en la salida del fichero, e
incluso hacer búsqueda de patrones de texto sin afectar la terminal. Por eso
`less` la secuestra, como si hubieramos abierto un programita que no tiene
salida gráfica y con el que se interacciona por la misma ventana que la
terminal (de hecho, así es). Para salir de `less` basta con presionar la tecla
'q', pero vamos a imaginar ahora que `less` no responde... se atoró porque el
fichero es muy grande. Le hemos pedido por ejemplo a `less` que haga una
búsqueda de patrón de texto, pero la cantidad de información es tanta que le
está tomando mucho tiempo y nos hemos arrepentido... haremos la búsqueda con
`awk`. ¿Cómo interrumpimos el proceso? ¿Cómo lo matamos?

Vamos a generar, antes que nada, nuestro gran fichero. Veremos más adelante que
Bash es un lenguage de programación donde puedo hacer todo tipo de cosas, como
bucles por ejemplo:

```bash
for i in `seq 1 10`;
   do
      echo $i
   done
```

o lo que es lo mismo:

```bash
for i in `seq 1 10`; do echo $i; done
```

Vamos a emplear un bucle para hacer un gran fichero de un 10 millones de
números aleatorios -le costará un minuto escribirlo en disco-:

```bash
for i in `seq 1 10000000`; do echo "En la linea" $i "el número aleatorio" $RANDOM >> numeros_aleatorios.txt ; done
```

El fichero es grande. Pesa más de 400 megas. Puedes ver el tamaño que ocupa en
disco con el comando:

```bash
du -sh numeros_aleatorios.txt
```

Y si quieres saber cuantas líneas o caracteres tiene:

```bash
wc -l numeros_aleatorios.txt
wc -c numeros_aleatorios.txt
```

Ahora vamos a abrirlo con `less` para buscar la línea que contiene el patrón
`la linea 1000000`. Para ello:

```bash
less numeros_aleatorios.txt
```

Con `less` abierto sobre nuestro fichero teclea `/la linea 1000000` y presiona
la tecla 'entrar'. Verás que tarda un par de segundos en leer secuencialmente
el fichero hasta que encuentra el texto que buscamos. Busquemos ahora
'10000000'. Para repetir la operación desde el principio, sal de `less` con la
tecla 'q', vuelve a abrir el fichero y teclea `/10000000`. Verás que tarda un
poquito. Vamos a suponer que queremos abortar la búsqueda porque el fichero es
excesivamente grande. Con `less` abierto sobre nuestra terminal vamos a
encontrar buscar su PID. Abre otra terminal y ejecuta:

```bash
ps aux
```

Verás que se listan todos los procesos que están corriendo en tu computadora en
este momento. La primera columna ofrece el nombre del usuario propietario del
proceso, la segunda es el PID (número de identificación del proceso), y el
resto muestran información como la hora y el día de inicio, el tiempo que
llevan ejecutandose, la terminal a la que están vinculados, o el nombre o
comando del proceso mismo. Puedes encontrar información sobre estas columnas
haciendo [una sencilla búsqueda en
internet](https://www.google.com/search?q=ps+aux+columns).

Vamos ahora a buscar el proceso `less` para "matarlo" y liberar la primera
terminal. En lugar de revisar toda la lista, hagamos uso del poderoso comando
`grep` que nos ayuda a filtrar patrones de texto. Vamos a hacer lo que se
conoce en Linux como `pipe` o tubería, redirigiendo la salida de `ps aux` a la
entrada del comando `grep` (como si concatenáramos los dos):

```bash
ps aux | grep less
```

Obtendrás algo como:

```
diego    15949  0.0  0.0  11072  2572 pts/3    S+   13:57   0:00 less numeros_aleatorios.txt
diego    16454  0.0  0.0  15652  1160 pts/5    S+   14:07   0:00 grep --color=auto less
```

La segunda línea es el mismo comando `grep` que se está ejecutando, y '15949'
es el PID del proceso que queremos matar con el comando `kill`:

```bash
kill -9 15949
```

Verás que, como resultado, la primera terminal en la que se estaba ejecutando
`less` ha quedado liberada. Si te estás preguntando por qué añadimos `-9` al
comando `kill` puedes buscarlo en internet o acudir a la documentación propia
que acompaña a todos los comandos de Linux. Para esto ejecutamos el comando
`man`:

```bash
man kill
```

O puedes también encontrar una versión de la documentación más breve añadiendo
la bandera, en inglés *flag*, `--help`:

```bash
kill --help
```

Antes de pasar a la siguiente sección recuerda borrar el fichero
`numeros_aleatorios.txt`, es muy pesado. Antes de eso, deja que te cuente que
si querías ver cúal era el último número aleatorio registrado en el fichero, no
hacía falta hacer la búsqueda de la última línea con `less`. El comando `tail`
saca por pantalla el final de un fichero, así como `head` imprime las primeras
lineas:

```bash
tail numeros_aleatorios.txt
```

```bash
head numeros_aleatorios.txt
```

Vamos a jugar con los dos comandos para sacar por ejemplo la línea 9456:

```bash
head -9456 numeros_aleatorios.txt | tail -1
```

Ahora sí, no olvides borrar el fichero:

```bash
rm numeros_aleatorios.txt
```

## Los permisos de los ficheros.

Un fichero tiene asociado desde su creación unos permisos, negados o validados,
de escritura, lectura y ejecución; para el usuario propietario, el grupo
propietario o para todos. Vamos a ver esto con detalle.

El comando `touch` crea un fichero vacío, que en este caso vamos a llamar
'asdf'.

```bash
touch asdf
```

Para conocer los permisos y los propietaros podemos recurrir al comando `ls` con la bandera `-l`:

```bash
ls -l asdf
```

Veremos una linea similar a esta:

```bash
-rw-r--r-- 1 diego diego 0 dic  3 21:08 asdf
```

En la salida del comando anterior podemos identificar, empezando por el final,
el nombre del fichero, la fecha de su creación, el espacio que ocupa en disco
("0" porque está vacío) y dos veces 'diego', como usuario propietario y como
grupo propietario. Despues vemos el número entero "1" que indica el número de
enlaces -no relevante aquí-, y una secuencia de 10 caracteres:

- El primer carácter para un fichero normal suele ser '-'.
- Los siguientes tres caracteres 'rwx' indican permiso de lectura (r),
  escritura (w) y ejecución (x) para el usuario propietario. El permiso se
  indica como denegado para cada acción si en lugar de la letra correspondiente
  vemos un signo '-'.

- Los siguientes tres caracteres indican permiso de lectura, escritura y
  ejecución para el grupo propietario.

- Los últimos tres caracteres indican los mismos permisos pero para cualquier
  usuario.

Así, atendiendo a nuestro fichero 'asdf', vemos que tiene permisos de lectura y
escritura para 'diego', y únicamente de lectura para cualquier otro usuario.
Modifiquemos los permisos conociendo que en el siguiente comando la letra 'u'
quiere decir usuario, 'g' quiere decir grupo y 'a' hace referencia a cualquier
otro usuario. Vamos con `chmod` a dar permisos de ejecución para el usuario
'diego' y de escritura para cualquier otro.

```bash
chmod u+x asdf
chmod a+w asdf
```

Y aunque sea absurdo, vamos a quitarle los permisos de lectura al grupo propietario:

```bash
chmod g-r asdf
```

Veamos ahora la salida de `ls -l`:

```bash
-rwxr-xr-x 1 diego diego 0 dic  3 21:08 asdf
```

Por último, podemos cambiar el usuario o el grupo propietario con los comandos
`chown` y `chgrp` (y con `sudo`):

```bash
sudo chown liliana asdf
sudo chgrp liliana asdf
```

Por última vez ejecuta `ls -l`:

```bash
-rwx-w-rw- 1 liliana liliana 0 dic  3 21:09 asdf
```

Antes de continuar con la siguiente sección es conveniente que borres el
fichero 'asdf':

```bash
rm asdf
```


## Bash como lenguage de programación para la terminal. <a class="anchor" id="bash"></a>

En secciones anteriores hemos advertido que Bash es un lenguage de
programación. La terminal no es únicamente un medio para invocar comandos...
puedes programar algoritmos que resuelvan de un manera más eficiente la tarea
que pretendes resolver. Vamos a poner tres ejemplos sencillos: convertir como
pdf todas las imágenes con extensión png que se encuentren en un directorio,
listar todos los ficheros de tamaño mayor que un cierto límite en un
directorio, o ejecutar un proceso cuando otro haya terminado.

Antes de ver los ejemplos enunciaremos un poco de información sobre alguno de
los aspectos que caracteriza un lenguage de programación, como pueden ser las
variables, los bucles o las condiciones lógicas.

### Variables.

Como en todo lenguage de programación, la definición y almacenamiento de
variables es esencial. Puedes definir variables en la terminal de la siguiente
manera:

```bash
var_A='patata'
var_B=4
```

Puedes con `echo` sacar por la terminal el contenido de las variables:

```bash
echo $mi_variable
echo $otra_variable
```

Puedes realizar operaciones algebráicas con las variables:

```bash
var_C=$(($var_B + 2))
echo $C
```

No es el objetivo de este texto enseñar a programar en Bash. Se trata
únicamente de que comprendas por qué es más util trabajar con la terminal que
con el entorno de escritorio. Puedes encontrar en internet guías y tutoriales
de programación en Bash si quieres profundizar. Allí aprenderas que también
puedes definir variables lógicas, vectores, etc. 

Antes de terminar la introducción a las variables, has de saber que estas
variables que defines en una terminal están asociadas a esa terminal... en
cuanto la cierres se van a perder, y si pasas a otra terminal no las vas a ver.
Son locales.

Linux hace uso también de las variables para la gestión de los procesos y los
usuarios. Muchas de las cosas que están detrás de un usuario son variables. El
nombre de tu usuario, el conjunto de paths en los que tu usuario busca comandos
o archivos ejecutables, la lista de paths donde tu usuario busca librerías, el
path en el que se encuentra tu terminal, el path de tu directorio hogar... son
variables:

```bash
echo $USERNAME
echo $PATH
echo $LIBRARY_PATH
echo $PWD
echo $HOME
```

Puedes listar todas las variables que tu terminal maneja con el comando
`export`:

```bash
export
```

De hecho, `export` o `set` también sirven para la definición de variables:

```bash
export varD=10
```

Puedes borrar las variables de la memoria de la siguiente manera:

```bash
unset varD
```

### Bucles.

Hemos visto aquí un ejemplo en las secciones anteriores. Puedes hacer bucles en
Bash del tipo secuencia, "haz mientras que...", "haz en caso de que...", etc.
Vamos a ver un ejemplo de tipo secuencia y otro de tipo "haz mientras que...":

```bash
j=0
for i in $(seq 0 5 25)
do
   j=$(($j + 1))
   echo "El número $j de la serie es $i"
done
```

```bash
j=0
while [ $j -le 5 ]; do
   i=$(($j * 5))
   j=$(($j + 1))
   echo "El número $j de la serie es $i"
done
```

### Condicion lógica *if*. <a class="anchor" id="if"></a>

También existen las condiciones lógicas. Veamos dos ejemplos de la sintaxis de
la condición lógica "si ocurre esto haz esto otro". Nos auxiliaremos para el
primero del comando `date`. Pruébalo antes:

```bash
date
```

`date` tiene muchas opciones, puedes checar `date --help` para entender qué
significa:

```bash
date+"%u"
```

Podemos redirigir la salida de un comando a una variable en lugar de a
`stdout`. Parecido a como la podíamos dirigir a un fichero de disco mediante
`>`, pero esta vez a una variable:

```bash
dia_de_la_semana=`date +"%u"`
```

Hagamos ahora un ejemplo de estructura condicional con esta variable:

```bash
if [ $dia_de_la_semana -le 4 ]; then
    echo 'Muy bien. Es día laborable y estás trabajando.'
elif [ $dia_de_la_semana -eq 5 ]; then
    echo 'Es viernes!'
elif [ $dia_de_la_semana -le 7 ]; then
    echo 'Estás trabajando en fín de semana?'
else
    echo 'Tu semana tiene más de 7 días?'
fi
```

Ya estamos en condiciones de resolver algunas tareas sencillas.

### Conversión de imágenes encontradas en un directorio. <a class="anchor" id="convert"></a>

Como primer ejemplo vamos a escribir unas líneas que ejecutar en la terminal
para convertir los ficheros jpg de un directorio a pdf con unas pocas lineas de
código.

En primer lugar descarga un paquete de imagenes jpg gratuitas que hemos
recopilado para este tutorial:

```bash
wget https://github.com/uibcdf/Academia/raw/main/data/misc/free_images_jpg.tar.gz
```

Se trata de un archivo comprimido (tar.gz), si buscas en internet como
descomprimirlo vas a encontrar algo como:

```bash
tar -zxvf free_images_jpg.tar.gz
```

Ahora vamos a situarnos en el directorio donde están las imágenes. Además, para
ver que nuestro bucle opera solo sobre los ficheros jpg, vamos a crear tres
ficheros allí que no deberían verse afectados.

```bash
cd free_images_jpg
touch foo1.txt foo2.png foo3.exe
ls
```

Hagamos un bucle para convertir las imágenes jpg a pdf. Usaremos el comando
`convert` que puedes instalar con el paquete llamado `imagemagick`. Recuerda
que si estás usando Ubuntu, basta el comando `sudo apt install imagemagick`
para instalarlo. Desafortunadamente, para aprovechar todas sus funcionalidades,
hay algo más. Por motivos de seguridad ImageMagick viene con la opción de
tratar pdfs bloqueada, para resolverlo tendrás que seguir [las indicaciones
dadas por un usuario en este foro](https://stackoverflow.com/a/52831300).

Ahora sí, ejecuta estas líneas de código Bash:

```bash
for filename in *.jpg; do
    fileprefix=`basename $filename .jpg`
    echo "Convirtiendo $fileprefix de jpg a pdf..."
    convert $filename $fileprefix.pdf
done
```

Verás que los archivos jpg se han convertido a pdf:

```bash
ls
```

Puedes abrir un pdf con por ejemplo el comando `evince`:

```bash
evince alpine-architecture-bridge-460373.pdf
```

No borres todavía la carpeta con estas imágenes. Van a ser de utilidad en la
siguiente sección.

### Listado de ficheros pesados.

Como segundo ejemplo hagamos un filtro para la lista de ficheros de una
carpeta. El criterio para cribar la lista de ficheros será que el tamaño sea
menor que cierto límite. Si descargaste, como se proponía en el ejemplo
anterior, el paquete de imágenes jpg gratuitas, podemos trabajar sobre ese
mismo directorio. Veamos un límite razonable para que tenga sentido:

```bash
du -sh *
```

Vemos que el límite de 1500K puede funcionar como filtro:

```bash
mi_filtro_de_tamaño=1500
for filename in *; do
    peso=`du $filename | awk '{print $1}'`
    if [ $peso -gt 1500 ]; then
        echo "      $filename ($peso K)"
    fi
done
echo "Hecho."
```

Por último, y para no acumular ficheros innecesarios, puedes borrar lo que
hemos generado para este ejemplo y el anterior:

```bash
cd ../.
rm -r free_images_jpg free_images_jpg.tar.gz
```

### Finalización de un proceso como gatillo para otro. <a class="anchor" id="gatillo"></a>

Como último ejemplo, hagamos un sencillo algoritmo de proceso que se dispara
cuando otro acaba. Hagamos, como situación ilustrativa, que una terminal
imprima un mensaje cuando el comando `less`, ejecutado en otra terminal, acabe.

Abre una terminal, colócala al izquierda de tu pantalla y ejecuta `less` sobre
un fichero que vamos a crear:

```bash
echo "Este fichero es auxiliar" > foo.txt
less foo.txt
```

Ahora, sin cerrar `less`, abre otra terminal y colocala a la derecha de la
pantalla. Sobre ella vamos a ejectuar unas líneas de código que ordenan a la
terminal esperar a que no exista ningún proceso activo que contenga el texto
'foo.txt' para imprimir un mensaje. Copia estas lineas sobre la terminal
derecha y ejecútalas.

```bash
less_vivo=0
while [ $less_vivo -eq 0 ]; do
    sleep 1
    ps aux | grep -v 'grep' | grep 'foo.txt' > /dev/null
    less_vivo=$?
    if [ $less_vivo -eq 1 ]; then
        echo "El proceso terminó!"
    fi
done
```

Verás que la terminal espera con el cursor parpadeante. Ahora, con las dos
terminales a la vista, mira lo que sucede en la terminal derecha cuando
seleccionas la terminal izquierda y presiona la tecla 'q' para salir de `less`.

## Las extensiones de los archivos.

El nombre de un fichero usualmente lleva un sufijo precedido por un punto. Por
ejemplo 'fichero.txt' o 'fichero.sh' o 'fichero.py'. Ese sufijo, denominado
también extensión, sirve para indicar al usuario y al sistema qué naturaleza
tiene el fichero (y con qué aplicación debe abrirse por defecto). Pero no
pierdas de vista que no es nada más que parte del nombre del fichero y responde
a un convenio. Podemos crear un fichero de texto y llamarlo 'patata' o
'patata.txt', en ambos casos lo vas a poder leer con `less` o `more`. Podemos
crear el fichero 'patata' o 'patata.sh' en el caso de un script de bash, y
ambos comandos `bash patata` o `bash patata.sh` tendrán el mismo efecto. O
podemos crear un script de python y llamarlo 'patata' o 'patata.sh' o
'patata.txt' o 'patata.py'... todos ellos podrán ser leidos por el
interpretador `python` con el mismo efecto. Por último, puedes tomar el pdf
'patata.pdf' y llamarlo 'patata.odt' y el comando `evince patata.odt` abrirá el
pdf igual que lo haría `evince patata.pdf`. Reitero, la extensión es sólo una
parte del nombre, y tiene una función indicativa, no condiciona su contenido.

En la siguiente sección veremos que un fichero no es ejecutable por tener la
extensión '.exe', si no por tener permisos de ejecución.

## El script.

Hemos visto como Bash es en realidad un lenguage de programación. También que
esos comandos útiles listados en la sección ["La terminal y la sintaxis de
Bash."](#La-terminal-y-la-sintaxis-de-Bash.) no son más que 'programas'
ubicados en la carpeta `/bin`. Hemos ilustrado con ejemplos cómo la terminal
resulta tan útil, o más, que trabajar con el entorno de escritorio. Y vamos a
ver ahora otra tercera manera de operar con tu sistema operativo: el script.

A la terminal le podemos ofrecer ordenes de manera interactiva y secuencial, o
podemos escribir esa lista de ordenes en un fichero y pedirle que las ejecute
como un programa, línea a línea. Eso es un script: un fichero de texto plano
que codifica secuencialmente la lista de ordenes que queremos ejecutar y que se
ejecutan mediante la participación de un interpretador del fichero. En este
caso el interpretador de Bash. Que dónde está ese interpretador:

```bash
which bash
``` 

Hagamos unos ejemplos sencillos:

```bash
echo `echo "Eres la más lista"` > autoestima
```

Espero que hayas corregido el género de la frase si prefieres que te traten en
masculino. Ahora prueba a decirle a tu computadora que procese ese fichero con
el interpretador `bash`:

```bash
bash autoestima
```

`autoestima` es un script sencillo, de una sola línea. Vamos a hacerlo un
poquito más complicado antes de convertirlo en 'ejecutable'. Abre tu editor de
texto y escribe las siguientes líneas:

```bash
#!/bin/bash

# Genero un número aleatorio entre el 1 y el 5
loteria=`shuf -i 1-5 -n 1`

# Según el valor del número aleatorio saco un mensaje por terminal
if [ $loteria -eq 1 ]; then
    echo "Eres la más lista"
elif [ $loteria -eq 2 ]; then
    echo "Eres la más guapa"
elif [ $loteria -eq 3 ]; then
    echo "Eres la más simpática"
elif [ $loteria -eq 4 ]; then
    echo "Eres la más intelegente"
else
    echo "Eres la más divertida"
fi
```

¿Has visto la primera línea? No reconoces nada conocido, ¿verdad?. Esta primera
línea le dice a la computadora cúal es el interpretador que ha de leer el
script para convertirlo a lenguage máquina, a operaciones. Si la primera línea
no está, siempre podemos, como hicimos antes, invocar nosotros el intepretador
con el comando `bash` -si el script es de Bash-. Pero queremos que nuestro
fichero sea auto-ejecutable, y el usuario no tiene por qué saber que es de
`bash` o `python` o `perl`, por decir alguno.

Ahora sí, hagamos que `autoestima` sea un ejecutable:

```bash
chmod +x autoestima
```

Nota que seguramente `autoestima` ha cambiado de color en la terminal. Los
ficheros que no son directorios, ni alias o enlaces, ni ficheros comprimidos...
son de un color distinto que tu script. Esto es porque ahora tiene permisos de
ejecución. Mira el color con el que se lista en la terminal:

```bash
ls autoestima
```

Veremos más adelante qué significa el comando `chmod` en la sección ["Los
permisos de los ficheros."](#Los-permisos-de-los-ficheros.). Ahora ya puedes
ejecutar el script como un ejecutable, para ello tienes que invocarlo con el
path absoluto o el path relativo precedido de un '.':

```bash
./autoestima
```

```bash
/home/diego/autoestima
```

Volveremos al script 'autoestima' más adelante, no lo borres todavía.

Para que el script reconozca argumentos de entrada debemos usar las variables '1', '2', '3'... que
por defecto recogen el valor de dichos argumentos de entrada según su posición en un script de
bash.

Añade al script autoestima como primera linea:

```bash
echo $1
```

Y ejecútalo de la siguiente manera sustituyendo 'tu_nombre' por tu nombre:

```bash
./autoestima tu_nombre
```

## El reconocimiento y filtrado de texto: grep, awk y sed. <a class="anchor" id="grep"></a>

El segundo comando que vemos aquí, `awk`, es un poco más sofisticado a la hora
de hacer búsqueda de patrones de texto. Vamos a poner un ejemplo:

```bash
echo "Paso 0   Energía 10.4" > Experimento_626.oup
echo "Paso 0   Temperatura 303  Distancia 8.2" >> Experimento_626.oup
echo "Paso 1   Energía 10.2" >> Experimento_626.oup
echo "Paso 1   Temperatura 300  Distancia 8.1" >> Experimento_626.oup
echo "Paso 2   Energía 10.5" >> Experimento_626.oup
echo "Paso 2   Temperatura 306  Distancia 8.0" >> Experimento_626.oup
echo "Paso 3   Energía 10.1" >> Experimento_626.oup
echo "Paso 3   Temperatura 299  Distancia 7.8" >> Experimento_626.oup
echo "Paso 4   Energía 10.8" >> Experimento_626.oup
echo "Paso 4   Temperatura 302  Distancia 7.6" >> Experimento_626.oup
echo "Paso 5   Energía 10.1" >> Experimento_626.oup
echo "Paso 5   Temperatura 304  Distancia 7.5" >> Experimento_626.oup
```

Filtremos, como primer caso, según el número de campos. Antes de nada usemos
`awk` para sacar por pantalla el número de campos por línea después de las dos
primeras columnas

```bash
awk '{print $1, $2, NF}' Experimento_626.oup
```

Filtremos entonces las líneas que contienen sólo 4 campos:

```bash
awk '{if (NF==4) print $0}' Experimento_626.oup
```

Ahora, como último ejemplo que ilustra para qué puedes emplear `awk`, filtremos
las líneas en las que existe el patrón *Distancia* y su valor es menor o igual
que 8.0, e imprimamos dicho valor precedido únicamente del índice de paso:

```bash
awk '/Distancia/ {if ($6<=8.0) print $2, $6}' Experimento_626.oup
```

Ninguno de los dos comandos anteriores remplaza texto, bueno, con `awk` se
puede. Pero `sed` puede ser otra alternativa a usar con este propósito. Veamos
un ejemplo sencillo de substitución de texto con `sed`. En este caso, la
palabra *Distancia* por la palabra *Posición*.

```bash
sed 's/Distancia/Posición X/g' Experimento_626.oup
```

Puede que la sintaxis de estos comandos te pueda parecer un poco complicada
pero en internet es fácil encontrar tutoriales sobre su uso. Tanto `awk` como
`sed` son herramientas muy poderosas para el tratamiento de patrones de texto.
Hacen lo que hemos visto anteriormente, y mucho más. En principio no te
recomiendo que te detengas ahora para hacerte un super experto o experta de
`awk`, por ejemplo. Es mejor que continues tu proceso de formación y cuando
tengas la necesidad de usar el comando encuentres un tiempo para saber más. Por
el momento, es suficiente saber que existe y qué es lo que hace. 

