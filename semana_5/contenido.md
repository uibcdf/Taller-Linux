# Contenido

Los siguientes contenidos serán presentados en [una sesión de videoconferencia](sesion.md).
Puedes encontrar en [este enlace](slides/slides.pdf) las slides usadas como soporte.


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

## Ayuda de comandos con man, --help y apropos

Hemos visto en la sección anterior como `man`, o la bandera `--help`, sobre cualquier comando puede
dar algo de información sobre dicha orden. Vamos a ver ahora cómo la misma terminal puede
sugerirnos una lista de comandos según una búsqueda en su documentación. Pongamos por caso que
queremos unir dos ficheros pdf. ¿Qué podemos hacer si no tenemos internet ni otra documentación?
`apropos` nos puede ayudar. Digámosle a `apropos` que nos liste los comandos que tenemos instalados
en la computadora relacionados con la palabra 'pdf':

```bash
apropos pdf
```

El listado es largo, ¿verdad? Vamos a filtrar con la palabra 'join' (unir o juntar en inglés):

```bash
apropos pdf | grep join
```

En mi caso obtengo la siguiente propuesta de comando útil para nuestro propósito:

```
pdfjoin (1)          - join together pages from multiple PDF files
```

Puedo ahora encontrar más información sobre cómo se usa `pdfjoin` con `man`:

```bash
man pdfjoin
# puede salir con la tecla 'q'
```

O si te resulta muy extensa y sólo quieres un resumen de su uso:

```bash
pdfjoin --help
```


## Los enlaces simbólicos de fichero. <a class="anchor" id="ln"></a>

En Linux hay un tipo de fichero que únicamente sirve para apuntar a otro. Se llama enlace simbólico, funciona como un alias del fichero al que apunta y se declara con el comando `ln`. Veamos un ejemplo:

```bash
touch foo1
ln -s foo1 foo2
```

Hemos creado 'foo2' como enlace a 'foo1'. Puedes distinguir el original del enlace porque este último toma un color especial en la terminal:

```bash
ln -s foo?
```

También puedes saber a qué apunta un enlace con el comando `ls`:

```bash
ls -lah foo2
```

Así, cualquier modificación a 'foo2' será hecha en 'foo1':

```bash
echo 'Esta es una linea de texto' >> foo2
less foo1
```

De hecho, el enlace no tiene contenido y por lo tanto no ocupa memoria de disco. Puedes checar su tamaño con `du`:

```bash
du -sh foo2
```

Podemos hacer enlaces de cualquier tipo de fichero, incluidos directorios. Borremos los ficheros anteriores y hagamos un ejemplo con ficheros:

```bash
rm foo1 foo2
```

```bash
mkdir -p dir1/dir2/dir3
mkdir dirA
ln -s /home/diego/dir1/dir2/dir3 /home/diego/dirA/dir3 #nota que los paths deben ser absolutos
ls -lah dirA/dir3
touch dir1/dir2/dir3/nada
ls dirA/dir3
cd dirA/dir3
echo 'Con cien cañones por banda...' >> nada
less ../../dir1/dir2/dir3/nada
```

No podemos acabar esta sección sin responder algo que vienes preguntándote desde la generación del primer enlace simbólico: ¿Para qué la bandera `-s`? Hay dos tipos de enlaces, suaves o simbólicos (la `-s`) y rígidos. Los enlaces rígidos no los hemos tratado aquí. Los enlaces rígidos se declaran sin `-s` y tienen tres peculiaridades que los distinguen de los simbólicos. Primero, el original y el enlace deben estar en la misma partición. Segundo, no podemos hacer enlaces rígidos de directorios. Y tercero, si borramos el archivo original el enlace rígido sigue respaldando el contenido de dicho archivo, no queda huerfano. Al contrario del enlace simbólico, que queda sin contenido al borrar el archivo al que apunta.

## Los usuarios y los grupos.

Linux está diseñado desde su concepción para soportar sobre la misma máquina la actividad simultanea de varios usuarios. Esos usuarios tienen todos un número de identificación, un directorio hogar y una contraseña.

Tu número de identificación lo puedes encontrar con el siguiente comando:

```bash
id -u
```

Tu directorio hogar ya lo conoces, su path está en tu variable HOME:

```bash
echo $HOME
```

Tu contraseña la puedes cambiar con el comando `passwd`. Si quisieras hacerlo puedes ejecutar el comando en una terminal e introducir en primer lugar tu contraseña actual y luego la nueva.

```bash
passwd
```

Linux lleva el control de usuarios y sus características en el fichero '/etc/passwd'. Puedes echarle un ojo, si es la primera vez que lo haces vas a llevarte una sorpresa:

```bash
less /etc/passwd
```

¿Has encontrado tu usuario en esa lista? Hay muchos usuarios, ¿verdad? Hay usuarios que en realidad no son personas, no son usuarios reales. Se llaman demonios (en inglés *daemons*) y son aplicaciones que tienen un usuario virtual para realizar ciertas gestiones. Este hecho, que está en el nucleo del diseño del sistema Linux, es parte de lo que lo ha hecho tan eficiente con respecto a otros sistemas operativos.

Y además de usuarios, en Linux se definen grupos de usuarios. Esto es muy útil a la hora de gestionar acciones sobre conjuntos definidos de usuarios. Tu usuario, puede que todavía no lo sepas, pertenece a varios grupos. De hecho, tu usuario mismo define un grupo, con su número de identificación que seguramente será igual que el de usuario para para el registro de grupos. Puedes checarlo con el siguiente comando:

```bash
id -g
```

¿Y a que otros grupos perteneces? En el siguiente comando identificarás tu nombre e id de usuario, el nombre de tu usuario como grupo y su id, y la lista de grupos a los que perteneces:

```bash
id
```

¿Perteneces por ejemplo al grupo 'lpadmin'? Sólo los usuarios que pertenecen a ese grupo pueden hacer gestión de los recursos de impresión, como configurar la comunicación con una nueva impresora.

La lista de grupos se gestiona en casi toda distribución de Linux gracias al fichero '/etc/group':

```bash
less /etc/group
```

Por último, mira qué usuario está al comienzo de la lista de '/etc/passwd': root. En la siguiente sección abordaremos las cuestiones ¿Quién es root?, ¿Y quién además puede hacer tareas de gestión del sistema operativo? Te habrás dado cuenta de que en esta sección de usuarios y grupos no hemos dicho nada sobre cómo se crean. Es porque puede que no tengas permisos para realizar esas acciones. O sí.

## Root, el superusuario, y sudo. <a class="anchor" id="sudo"></a>
<br>
<center><img src="https://www.explainxkcd.com/wiki/images/b/b1/sandwich.png" width="25%"></center>
<br>

El usuario root, o superusuario, es el usuario definido en el sistema con permisos para realizar cualquier tarea. Es el usuario con la capacidad innata de administrar el sistema operativo. Hace un tiempo muchas distribuciones pedían a la hora de ser instaladas una contraseña para el usuario root. Suponiendo, claro, que la persona que instala el sistema operativo es el mismo que va a ejercer de administrador. Hoy en día, en el caso de Ubuntu por ejemplo, en la instalación se define un usuario con permisos de actuación "como si fuera" root. Es lo que se conoce como 'sudo'. Probablemente, si eres la persona que instaló el SO que estás usando y tu usuario es el primero que se creó, tu usuario tiene la capacidad de hacer `sudo`. De nuevo en el caso de Ubuntu, los usuarios con la capacidad de realizar tareas de administración como si fueran root deben pertenecer al grupo que lleva el nombre de 'sudo'. Puedes comprobar con el siguiente comando si perteneces a dicho grupo:

```bash
id
```

Si es el caso, puedes continuar de forma activa esta sección. Veamos por ejemplo que significa pertenecer al grupo 'sudo', o tener la capacidad de hacer `sudo`. Ejecuta el siguiente comando:

```bash
less /etc/shadow
```

Te dirá que no tienes permiso para ver su contenido. '/etc/shadow' contiene la encriptación de las contraseñas de los usuarios. Ahora prueba con el siguiente comando (pedirá tu contraseña de usuario):

```bash
sudo less /etc/shadow
```

En este caso estás ejecutando el comando `less` como si fueras root, como si fueras administrador, con plenos poderes para hacer cualquier cosa. Y ya sabes lo que le dijeron a Spiderman citando un discurso del expresidente estadounidense Franklin Delano Roosevelt: "... un gran poder conlleva una gran responsabilidad". Podrías por ejemplo generar un gran problema con el comando `sudo rm /etc/shadow`, o con el más desastroso de todos si no tienes copia respaldo de absolutamente todo: `sudo rm -r /*`.

Teniendo la posibilidad de ejecutar comandos con `sudo`, puedes, si tienes que realizar muchas tareas de administración que requieram ser superusuario, hacer uso del comando `su` para cambiar de tu usuario al usuario root. Antes de eso veamos que `su` también nos permite cambiar a cualquier otro usuario. Vamos a hacer un ejemplo de cambio a otro usuario antes de pasar a root. Primero vamos a crear un usuario nuevo que llamaremos 'thanos' desde la terminal:

```bash
sudo adduser thanos
```

Verás que pide que introduzcas la contraseña que usará 'thanos' además de otra información personal de caracter informativo -que puedes dejar en blanco presionando la tecla 'entrar'-. Ahora para comprobar que el usuario se ha creado satisfactoriamente hay muchas maneras. Por ejemplo, puedes cerciorarte de que su directorio hogar fue creado:

```bash
ls /home
```

Puedes también comprobar que su usuario aparece en el fichero '/etc/passwd':

```bash
less /etc/passwd | grep thanos
```

O puedes, porque tienes la capacidad de actuar como superusuario gracias al comando `sudo`, cambiarte por el...

```bash
sudo su thanos #la contraseña que pide es la de tu usuario... es sudo quien está asegurandose de que eres tu.
```

Et voilà! Ya eres thanos. Verás que el prompt cambió y ahora dice comienza con 'thanos@...' Puedes hacer cualquier cosa en la terminal y todo quedará registrado como 'thanos', porque de hecho, ahora mismo, eres 'thanos'. Pero 'thanos' no tiene permiso para usar `sudo`. Supongamos, únicamente como ejemplo de cómo puede hacerse, que queremos darle a 'thanos' permisos de superusuario. Ahora no tiene, prueba:

```bash
sudo less /etc/shadow
```

Sólo tu usuario, a través de `sudo`, y root pueden otorgarle ese poder. Así que sal de 'thanos' y vuelve a tu usuario, lo primero:

```bash
exit
```

¿Ya pone tu nombre de usuario en el prompt? Ahora ya puedes añadir a 'thanos' al grupo sudo. Siguiendo con el ejemplo de cómo se hace en Ubuntu:

```bash
sudo usermod -aG sudo thanos
```

Verás que ya pertenece al grupo privilegiado:

```bash
id thanos
```

Hagamos la prueba:

```bash
sudo su thanos   # sudo quiere saber si eres tu, es tu contraseña
sudo less /etc/shadow # sudo pide aquí la contraseña de thanos para asegurarse de que es él
```

De este modo le hemos dado a 'thanos' la posibilidad de modificar cualquier cosa en tu sistema operativo. Incluso, por ejemplo, de decidir qué usuario es aniquilado y qué usuario sobrevive. Pero antes de que él lo haga, borrémoslo a él para terminar el ejemplo. Para ello, sal de nuevo de 'thanos':

```bash
exit
```

Con tu usuario ahora elimina a 'thanos' y su directorio hogar:

```bash
sudo userdel thanos
sudo rm -r /home/thanos
```

Puedes comprobar, como hiciste antes, que 'thanos' ya no existe.

Por último, si tienes que realizar muchas gestiones de administración y no quieres estar a cada comando anticipándole el `sudo` puedes saltar al usuario root de este manera:

```bash
sudo su
```

Verás que el prompt ahora dice 'root@...'. Recuerda que siendo root tienes todo el poder, y una gran responsabilidad.

Para salir del superusuario root, basta con que hagas:

```bash
exit
```

