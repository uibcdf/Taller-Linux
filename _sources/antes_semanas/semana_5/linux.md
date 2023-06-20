## Editores de texto.

Hasta este punto, en esta unidad, hemos realizado la mayoría de las creaciones y modificaciones de ficheros de texto con el comando `echo`. Esto no es el del todo común -ni útil-. Se ha hecho así para evitar el tema de los editores de texto hasta llegar a esta sección.

Aclaremos qué entendemos aquí por editor de texto. Editor de texto es una aplicación que sirve para el registro de texto en las unidades de memoria. Todos los editores que vamos a mencionar tienen el mismo efecto, y todos realizan la función que los define con el mismo resultado. En general no podemos adivinar con qué editor fue escrito un fichero. La diferencia entre editores está en la experiencia de usabilidad.

Si eres un usuario poco experimentado puede que comiences sientiéndote más cómodo con editores sencillos que cuentan con modo gráfico (una ventana en el escritorio y un explicito menú de opciones). Un editor con estas características que está instalados por defecto en tu distribución puede ser `gedit`. Otros editores, como `nano`, convirten la misma terminal en un sencilla ventana de edición con un menú cuyas opciones son visibles y de fácil entendimiento. Te recomiendo que pruebes todos los editores antes de elegir el más cómodo.

Para ayudarte a que comiences inmediatamente a tener un sencillo editor con el que empezar a trabajar, aquí tienes cómo se invocan desde la terminal cualquiera de los dos anteriores (y como se cierran):

```bash
gedit foo.txt # se cierra con el menú de la barra superior de la ventana
nano foo.txt # se cierra con la combinación de teclas 'ctrl'+'x'
```

Hasta aquí la parte más sencilla. Ahora, si no lo sabes ya, debes saberlo. El mundo de los editores de texto es un mundo ámplio y espinoso. La edición de textos es la herramienta principal y fundamental de un programador. ¿Has visto unos videos en youtube titulados algo así como ['Trabajadores rápidos nivel dios'](https://www.youtube.com/watch?v=RYK7fKsL9XQ)? La mayoría de programadores y científicos computacionales pasan una enorme cantidad de horas al cabo de la semana trabajando en el editor de textos, por eso alcanzan un [nivel de dominio y comunión con el editor que resulta asombroso](https://vimeo.com/53144573). Cuando trabajas así, quieres que la edición de un archivo sea un proceso ágil. Quieres conocer las combinaciones de teclas y atajos que te facilitan el trabajo. Quieres que el editor te facilite la vida y no te retarde innecesariamente en tu trabajo. Por ejemplo, puede parecerte una tontería aunque seguramente lo experimentarás: el uso del ratón resulta molesto porque retarda la velocidad de edición al separar continuamente una mano del teclado. [Se trata de alcanzar el modo de trabajo óptimo en el que casi la edición de un texto sucede a la misma velocidad que se piensa. ¿Te imaginas?](https://github.com/PhungLuan/docs/blob/master/Drew%20Neil%20-%20Practical%20Vim%20Edit%20Text%20at%20the%20Speed%20of%20Thought%2C%202nd%20Edition%20-%202015.pdf)

Así, porque el editor de textos junto con la terminal han sido las herramientas de trabajo principales, igual que se han desarrollado distintas distribuciones de Linux, existen, se mantienen y siguen apareciendo una gran variedad de editores de texto. Desde finales de los años ochenta, dos editores de uso libre han mantenido una historica pugna entre la comunidad de usuarios: Vim y Emacs. La comunidad ha estado durante años dividida entre seguidores defensores uno y otro. Es lo que se ha llamado [la guerra de los editores](https://en.wikipedia.org/wiki/Editor_war). En la última década, o puede que un poco más, han aparecido otros editores (gratuitos y de pago) estéticamente más atractivos, con funciones y experiencias de uso muy agradables, aunque no todavía con la versatilidad y la comunidad de usuarios que te da una trayectoria de más de tres décadas. Hagamos unos breves comentarios a estos editores de texto "más profesionales". Será tu tarea elegir uno y aprender a manejarlo.

Todos estos editores reconocen, por la extensión del fichero, distintos formatos como pueda ser un programa en python, un fichero escrito en markdown, un fichero html, etc. Y dependiendo de este reconocimiento implementan funcionalidades como el coloreado de sintaxis del lenguaje, la posibilidad de completar comandos con tabulador, la detección de errores en el programa, etc. Todos ellos pueden transformarse en autenticos IDEs (del inglés Integrated Development Environment) proporcionando los mismos servicios integrales para programación que plataformas como [Eclipse](https://www.eclipse.org/ide/), [Xcode](https://developer.apple.com/xcode/ide/) o [Netbeans](https://netbeans.org/).

### Vi o Vim
[Vim](https://www.vim.org/) y [Emacs](https://www.gnu.org/software/emacs/) son la pareja de editores de texto por excelencia en Linux. [Vim](https://www.vim.org/) está instalado por defecto en casi todas las distribuciones, al menos en su versión más ligera, sencilla y antigua: Vi.

Aprender a manejar Vim para alcanzar un nivel de trabajo cómodo y eficiente toma su tiempo. Puedes encontrar numerosas bromas en internet sobre la curva de aprendizaje de Vim. Pero, al igual que con Emacs, con un poco de adiestramiento la edición de textos -y la programación- se vuelve una tarea más rápida.

Vim tiene la peculiaridad de que trabaja con una filosofía de 'modos'. Está por ejemplo el 'modo insertar texto', o el modo 'comandos' o el modo 'seleccionar texto'. De nuevo, al principio puede parecer molesto, pero con la práctica se le encuentra el sentido.

Vim es casi completamente modificable y personalizable en su uso, hackeable. Como cualquiera de los editores de esta lista. Por eso, la mayoría de usuarios arrastran a lo largo de su vida un fichero donde se definen los atajos, combinaciones de teclas, funcionalidades, implementaciones y modificaciones al comportamiento nativo, realizadas por uno mismo o encontradas en foros de internet.

Vim es uno de los editores de texto para terminal que más rápido te permite abrir un fichero, hacer una pequeña edición, guardar y volver a la terminal.

### Emacs
[Emacs](https://www.gnu.org/software/emacs/) es el otro contendiente en la histórica guerra de editores de texto. 

Emacs, como Vim, también requiere un poco de paciencia al principio. Tras unas horas de práctica alcanzarás un nivel de uso que cubrirá de manera rápida tus necesidades más habituales, pero si quieres seguir aprendiendo y optimizando tu edición de textos, estos dos editores te ofrecen unas posibilidades inmensas. Sólo después de años de uso, si es que no te lo tomas de manera muy intensa, llegas a apreciar los límites de cada editor.

Emacs no trabaja desde una filosofía de 'modos' de edición. Emacs tiene un amplio repertorio de combinación de teclas y opciones de entrada de comandos que cubre casi cualquier necesidad. Además Emacs tiene en su nucleo una especie de sistema operativo que lo hace adaptable a cualquier necesidad. Con la posibilidad de implementar modificaciones para cualquier función. Por poner unos ejemplos sencillos que puedas entender, con emacs tienes la posibilidad de [visualizar por ejemplo un pdf](https://www.emacswiki.org/emacs/DocViewMode) o de [publicar un tweet en tu cuenta de twitter](https://www.emacswiki.org/emacs/TwitteringMode) sin salir del editor.

Vim o Emacs son dos muy buenos editores. Si no fuera así no hubieran sobrevivido tantos años en una comunidad tan exigente.

### Spacemacs o Spacevim

Han surgido varios intentos de editor de texto híbridos entre Vim y Emacs. Editores que puedan toman lo mejor de cada uno de ellos, o que te permiten personalizar el grado de "vimificación" o "emacsficación" con el que estás trabajando. Un ejemplo es [Spacemacs](http://spacemacs.org/), y más tarde [Spacevim](https://spacevim.org/). Spacemacs es un emacs con una filosofía de modos integrada como la de Vim. Puedes elegir dos sabores de uso, 'glory', con un universo de atajos y combinaciones de teclas similar al Emacs original y 'hell', con una experiencia de uso más parecida a Vim.

Su arranque, dado que carga muchas librerías, puede resultar un poco lento.

### Atom

[Atom](https://atom.io/) es un moderno editor de texto de uso libre con una estética más actual y unas funcionalidades que le pueden hacer competir con Vim o Emacs. Nació directamente en GitHub como un proyecto de editor moderno de uso libre para desarrolladores.

Atom no está instalado por defecto y puede que no lo encuentres en el repositorio de tu distribución de Linux. Pero lo puedes instalar en MacOs, Windows o Linux facilmente desde [su web](https://atom.io/).

### Sublime

[Sublime](https://www.sublimetext.com/) es un editor de uso no libre, de pago. La especial orientación de Sublime para la edición de código de programación y sus funciones como IDE, han hecho que gane en los últimos años una enorme popularidad entre profesionales del cómputo, programadores y usuarios avanzados.

<br>
<center><img src="https://imgs.xkcd.com/comics/real_programmers.png" width="50%"></center>
<br>

<br>
<center><img src="https://imgs.xkcd.com/comics/types_of_editors.png" width="50%"></center>
<br>

<br>
<center><img src="https://imgs.xkcd.com/comics/hottest_editors.png" width="25%"></center>
<br>

## Los ficheros de configuración de usuario. <a class="anchor" id="configuracion_usuario"></a>

Los ficheros de configuración de cada usuario están ocultos en su directorio 'home'. ¿Cómo se oculta un archivo en Linux? Un archivo se oculta comenzando su nombre con un '.', y para listarlos y verlos hay que añadir a `ls` la bandera `-a` (del inglés *all*):

```bash
ls -a
.   .bash_history  .bashrc  .profile
..  .bash_logout   .cache   .gnupg
```

Es cierto que hay parámetros de configuración de un usuario que se encuentran en los ficheros del sistema. Porque se definen como opciones "por defecto" válidas para todo usuario. Pero en la jerarquía de los ficheros que definen el comportamiento de tu usuario, siempre tiene prioridad lo que puedas definir en tus ficheros. Hablaremos de los más importantes:

#### ~/.bashrc

Es el archivo más importante que tienes para definir el comportamiento de tu usuario. Cada vez que abres una terminal, este fichero se ejecuta. ¿No te lo crees? Vamos a hacer un prueba. Abre tu '.bashrc' con un editor para incluir al final del fichero estas tres lineas:

```
export mi_variable='tururú'
alias cuantos_ficheros_hay_en_esta_carpeta='ls -l | wc -l'
echo "Hola! Ya terminé de ejecutar el .bashrc"
```

Guarda, cierra el fichero y abre una nueva terminal. Verás que antes de colocar el primer prompt la terminal muestra el resultado del último comando que añadirmos al final de '.bashrc'. Ahora prueba que las otras dos líneas que añadimos se ejecutaron.

```bashrc
## Saca el contenido de la nueva variable
echo $mi_variable
```

```bashrc
## No hace falta que lo escribas todo, la tecla 'tab' completará el comando
cuantos_ficheros_hay_en_esta_carpeta
```

Ahora que ya viste en acción la función de este fichero, puedes volver a abrirlo y borrar esas lineas.

#### ~/.bash_aliases

Algunas distribuciones de Linux configuran la plantilla de '.bashrc' que se colocará en cada nuevo usuario. Puedes comprobar, como seguramente le sucede a tu '.bashrc', que incluye la siguiente instrucción:

```bash
if [ -f ~/.bash_aliases ]; then
    . ~/.bash_aliases
fi
```

Si leistes las secciones anteriores, puedes adivinar que lo que está haciendo ese segmento de código es comprobar si en tu directorio hogar existe el fichero '.bash_aliases', y si es así, lo ejecuta. Es una manera de que '.bashrc' no se haga inmensamente largo y puedas organizar la configuración de tu usario un poco. De este modo, las definiciones de alias las sacaremos de '.bashrc' y las pondremos en '.bash_aliases'. Y no, no hemos olvidad que todavía no dijimos nada aquí de qué es un alias, pero lo pudiste deducir de nuestro ejericio con '.bashrc'. Un alias es eso, un alias. Es renombrar un comando con otra cadena de caracteres para que pueda ser invocado de una manera más comoda, más rápida y más facil de recordar. 

Hay alias definidos casi en todas las distribuciones de Linux como son:

```bash
alias ls='ls --color=auto' # ls dará color a los ficheros según su naturaleza
alias ll='ls -alFh'        # ll listará todos los ficheros junto con permisos y tamaño en formato leible por humanos
alias la='ls -A'
alias l='ls -CF'
```

Te dejo como tarea acudir a internet, a `ls --help` o `man help` para averiguar el significado de los dos últimos alias.

#### ~/.profile
Este fichero es muy similar a './bashrc'. En realidad en algunas distribuciones como Ubuntu, este fichero se ejecuta antes. Este es el fichero que ordena ejecutar './bashrc' si es que lo tienes. Verás que './profile' contiene:

```bash
# if running bash
if [ -n "$BASH_VERSION" ]; then
    # include .bashrc if it exists
    if [ -f "$HOME/.bashrc" ]; then
        . "$HOME/.bashrc"
    fi
fi
```

Este parrafo comprueba primero que la computadora tiene Bash instalado, y en ese caso busca que el usuario tenga un fichero '.bashrc'. Si esto último sucede, lo ejecuta.

Podemos usar '.profile' para la personalización de variables de entorno. Veremos un ejemplo de esto en la siguiente sección.

#### ~./bash_history

Este no es exactamente un fichero de configuración, pero le debemos reconocer mucha utilidad. `~/.bash_history` guarda la secuencia de los $N$ últimos comandos ejecutados por tu usuario. Como su nombre indica, es un histórico. Prueba antes que nada en tu terminal a mantener presionada la tecla 'ctrl' mientras pulsas varias veces la tecla 'p'. ¿No estás viendo los últimos comandos que realizaste?, ¿no estás caminando hacia atrás en tu historico? Prueba ahora otra cosa. Borra la linea que 'ctrl'+'p' dejó en la terminal y ahora haz 'ctrl'+'r'. ¿Te aparece algo así?

```bash
diego@nauta:~$ 
(reverse-i-search)`': 
```

Puedes ahora teclear una cadena de caracteres y que se buscarán de manera reversa en el histórico. Vamos a probar a ver cúal fue el último comando que empezaba con 'echo'. Teclea 'echo' si tu terminal dice `reverse-i-search`. ¿Ya salió? Ahora, con la tecla 'ctrl' presionada pulsas varias veces 'r', verás que aparecen la serie de comandos que contienen los caracteres 'echo' en búsqueda reversa del historico. Ya puedes borrar la linea que la búsqueda reversa te dejó.

Entonces, ¿dónde 'ctrl'+'p' o 'ctrl'+'r' encuentra tu historial de comandos?:

```bash
.bash_history
```

Pero este fichero tiene una cantidad de líneas limitada. Comprueba cual es la longitud, en cantidad de líneas, que tiene tu fichero:

```bash
wc -l
```

`wc` sirve también para contar la cantidad de caracteres de un fichero de texto:

```bash
wc -m .bash_history
```

Para modificar la cantidad de información que puede quedar registrada en tu histórico tendrás que editar las variables `HISTSIZE` e `HISTFILESIZE` en tu fichero '.bashrc'. Qué hace cada variable lo puedes encontrar en la documentación o foros como [este](https://stackoverflow.com/questions/19454837/bash-histsize-vs-histfilesize). En mi caso yo modifiqué el valor de esas variables para tener un histórico razonable en el que poder buscar los comandos que ejecuté en el pasado.

```bash
HISTSIZE=200000
HISTFILESIZE=200000
```

Por último y antes de pasar a la siguiente subsección, un consejo: 'ctrl'+'p' y 'ctrl'+'r' pueden hacer que tu interacción con la terminal sea más cómoda. Yo los uso con frecuencia para trabajar más ágil, ¿Para qué voy a teclear de nuevo el comando anterior?, ¿para qué vamos a teclear entero el comando que fué ejecutado hace unos minutos?

#### Otros ficheros

Distintas distribuciones de Linux organizan la información de distinta manera. Aquí estamos siendo un poco más fieles a la distribución Ubuntu porque es la que hemos recomendado para un usuario no experto que necesita un entorno de trabajo estable y productivo en el laboratorio. Puede que tengas otra distribución y veas ficheros como `.bash_profile` o `.bash_login`. En internet vas a encontrar fácilmente información sobre su función.

## Las variables de entorno.

Hemos hablado anteriormente de las variables en Linux. También de las variables de usuario como `HOME` o `PWD`. Estas últimas son variables de entorno. Son variables que definen el comportamiento de tu usuario y la terminal, en definitiva, el comportamiento del entorno Linux. Quizá las que debes de conocer de cara al trabajo que realizamos sean `PATH`, `LIBRARY_PATH` y `LD_LIBRARY_PATH`. Estas tres variables afectan a cómo interaccionas con el software y las librerías que vas a instalar para trabajar.

### PATH

`PATH` almacena, separados por el caracter ':', la lista de directorios en los que tu usuario buscará ejecutables (comandos). Prueba:

```bash
echo $PATH
```

¿Ves el directorio '/bin' en la lista? Tu usuario puede ejecutar `ls` o `echo` porque estos son comandos que encuentras en alguno de los directorios que tu usuario almacena en `PATH`:

```bash
ls /bin
```

### LIBRARY_PATH y LD_LIBRARY_PATH

Así como `PATH` contiene los sitios donde encontrar ejecutables, `LIBRARY_PATH` contiene la lista de lugares con librerías necesarias para compilar un ejecutable y `LD_LIBRARY_PATH` la lista de lugares con librerías dinámicas a las que cualquier programa o ejecutable puede acudir para realizar funciones concretas.

### Más variables de entorno?

Sin duda hay más variables de entorno, pero no tienes por qué conocerlas todas para ser un usuario avanzado. No es el propósito tampoco de este notebook hacer un repaso riguroso. Puedes encontrar información fácilmente en internet, y acudir a ella cuando se presente la ocasión y lo necesites.

Lo que sí debes saber es que estas variables pueden ser modificadas a conveniencia. Vamos a ver un ejemplo para que lo comprendas mejor. ¿Recuerdas el script 'autoestima'? Lo programamos y declaramos ejecutable en la sección ["El script."](#El-script.). Ahora vamos a colocar una copia de dicho script en alguno de los directorios de tu lista `PATH`. ¿Qué tal en el directorio '/usr/bin' o '/usr/local/bin'?:

```bash
cp autoestima /usr/bin/.
```

No funcionó, ¿verdad? Claro, no cualquier usuario puede alterar el contenido de '/usr/bin'. Necesitas permisos de administración, ¿si los tienes?

```bash
sudo cp autoestima /usr/bin/.
```

Ahora abre una terminal nueva e imagina... estás trabajando con la moral baja y necesitas una inyección de autoestima. ¡Ya puedes teclear con la terminal situada en cualquier directorio 'autoestima'!

```bash
autoestima
```

Borra mejor el script. Tu no lo necesitas...

```bash
sudo rm /usr/bin/autoestima
```

Pero para conseguir esto no hace falta que tengas permisos de administración, al fín y al cabo sólo quieres hacer algo que afecta a tu usuario. Y el mal uso de `sudo` puede ser un riesgo que afectará a todos en esa máquina. Vamos crear un directorio tuyo en el que todos los ficheros que ubiques allí serán interpretados por tu usuario como comandos y ejecutables:

```bash
mkdir /home/diego/mibin
```

Ahora mueve el script 'autoestima' a ese directorio:

```bash
mv autoestima ~/mibin/.
```

Sólo queda añadir el path '/home/diego/mibin' a la variable `PATH`.

Abre el fichero `.profile` o el `.bashrc` con tu editor e incluye al final de él algo como:

```bash
### Mis Paths

export PATH=$HOME/mibin:${PATH}

```

Cualquier terminal que abras a partir de ahora tendrá en su lista de lugares en los que encontrar ejecutables el path de tu directorio `mibin`. Abre una terminal nueva y prueba:

```bash
echo $PATH
```

Ya apareció ahí tu directorio 'mibin', ¿verdad? Pues ya puedes dejar que la computadora te suba la autoestima cuando quieras:

```bash
autoestima
```

## SSH y la conexión con otras máquinas. <a class="anchor" id="ssh"></a>

SSH, del inglés *Secure Shell*, es el protocolo de comunicación encriptado más común para interaccionar con otras computadoras. SSH te permite operar remótamente con otra máquina a través de tu terminal. Para ello el comando `ssh` necesita la IP de la máquina destino y el usuario registrado en esá máquina que usarás para acceder

```bash
ssh liliana@155.192.168.1
```

El comando anterior hace una llamada a la máquina 155.192.168.1 y le pide acceso como usuario 'liliana'. Acto seguido se nos pedirá la contraseña de liliana en esa máquina para despues licitar nuestra terminal con el mismo grado de operabilidad en la máquina destino como si de la local se tratase. De hecho, verás que el prompt cambia para indicar ahora el nombre ('hostname') de la máquina remota, y el usuario con el que operas:

```bash
liliana@nombre_máquina_remota:~$
```

Ya puedes, en remoto, ejecutar los comandos que necesites en ese máquina. Ahora, para cerrar la conexión y volver a tu máquina local:

```bash
exit
```

Puedes también copiar ficheros desde tu máquina local a la remota, y viceversa. Para ello el protocolo SSH dispone del comando `scp`. De manera similar a cómo opera `cp`, `scp` puede copiar un fichero local a una máquina remota:

```bash
scp /path/a/fichero/fuente usuario@ip:/path/de/destino/.
```

O de la máquina remota a la máquina local:

```bash
scp usuario@ip:/path/a/fichero/fuente /path/de/destino/.
```

### Puedes operar con hostnames en lugar de IPs

Las direcciones IP pueden tener definidas alias en tu máquina. De esta manera no hace falta que las memorices, basta con que las listes en el fichero '/etc/hots':

```bash
less /etc/hosts
```

¿Tienes una máquina a la que accedes habitualmente? Supongamos que se llama AllSpark y que su ip es la 999.999.999.999. Edita el fichero '/etc/hosts' con tu editor de textos y añade la siguiente linea:

```bash
999.999.999.999 allspark
```

Ya puedes emplear `ssh` y `scp` sustituyendo la ip de la máquina remota por su hostname. Por ejemplo:

```bash
ssh liliana@allspark
```

## Nota final.

El contenido de este documento es suficiente para comenzar. Ya sólo queda que a medida que vayas trabajando, poco a poco aprendas aquellos comandos que más usas. Al principio no hay que desesperarse, probablemente necesitarás varias veces volver a buscar qué comando servía para borrar un directorio, o qué comando servía para filtrar la salida de `less`... pero con un poco de paciencia irás familiarizandote con la terminal. Todos los usuarios estamos constantemente aprendiendo cosas nuevas y recordando otras. Pero pront se adquiere un nivel de uso que compensa sobradamente el tiempo invertido. Ahora, lo único importante es que hayas tenido un primer contacto para entener qué te puede ofrecer el uso de Linux.

---

## Dudas, problemas técnicos y soluciones. <a class="anchor" id="dudas"></a>

Para centralizar esas dudas, sugerencias o soluciones técnicas sobre el tema de este notebook, haz uso del siguiente canal:

[Foro Técnico: Linux](https://github.com/uibcdf/Academia/issues/9)


## Más recursos útiles <a class="anchor" id="recursos"></a>

Esto era sólo una guia introductoria. No es funcional documentarse o estudiar mucho sin antes comenzar a usar el sistema operativo Linux. Aprenderás de manera más solida si con el uso te van surgiendo necesidades a las que vas dando solución poco a poco. Si la computadora es tu herramienta de trabajo, es tu deber conocerla. Puedes encontrar -o contribuir añadiendo- más información útil en el siguiente listado.

### Documentación <a class="anchor" id="documentacion"></a>
https://en.wikipedia.org/wiki/List_of_Linux_distributions    
https://www.linux.com/    
https://www.linux.com/what-is-linux    
https://en.wikipedia.org/wiki/Linux    
https://www.linux.org/    
https://en.wikipedia.org/wiki/Unix_shell    
https://www.tldp.org/LDP/intro-linux/html/index.html    
https://www.linux.com/blog/learn/intro-to-linux/2018/4/linux-filesystem-explained   
https://www.tecmint.com/linux-file-system-explained/   

### Tutoriales, Webinars y cursos gratuitos <a class="anchor" id="tutoriales"></a>
http://swcarpentry.github.io/shell-novice-es/    
http://swcarpentry.github.io/shell-novice/    


<br>

<div style='text-align: right;'> <a href="../Buenas_practicas/Buenas_practicas.md">Ir a la siguiente unidad</a> </div>

-------
<p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/uibcdf/Academia">UIBCDF-Academia</a> por <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://github.com/uibcdf/Academia/graphs/contributors">UIBCDF Lab, autores y colaboradores</a> es material protegido bajo una licencia <a href="http://creativecommons.org/licenses/by-nc-sa/4.0/deed.es?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">Attribution-NonCommercial-ShareAlike 4.0 International<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/nc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/sa.svg?ref=chooser-v1"></a></p>

[distrowatch_popularity]: https://distrowatch.com/dwres.php?resource=popularity
[distrowatch_major]: https://distrowatch.com/dwres.php?resource=major
[ubuntu]: https://www.ubuntu.com/
[ubuntu_download]: https://www.ubuntu.com/download/desktop
[elementaryos]: https://elementary.io/
[archlinux]: https://www.archlinux.org/
[centoos]: https://www.centos.org/
[system76]: https://system76.com/pop
[linuxmint]: https://linuxmint.com/
[debian]: https://www.debian.org/
[redhat]: https://www.redhat.com/en
[mandriva]: https://www.openmandriva.org/
[freebsd]: https://www.freebsd.org/
[gentoo]: https://www.gentoo.org/
[slackware]: http://www.slackware.com/
[fedora]: https://getfedora.org/
[opensuse]: https://www.opensuse.org/
[try_ubuntu_before_install]: https://tutorials.ubuntu.com/tutorial/try-ubuntu-before-you-install#0
[tutorial_install_ubuntu_desktop]: https://tutorials.ubuntu.com/tutorial/tutorial-install-ubuntu-desktop#0
[tutorial_usb_booteable]: https://tutorials.ubuntu.com/tutorial/tutorial-create-a-usb-stick-on-windows#0
[installation_guide_blog]: https://www.linuxtechi.com/ubuntu-18-04-lts-desktop-installation-guide-screenshots/
[journaling]: https://help.ubuntu.com/community/LinuxFilesystemsExplained
[fat_allocation_table]: https://web.archive.org/web/20150925082826/http://www.wizcode.com/articles/comments/a-brief-introduction-to-fat-file-allocation-table/
[ntfs_vs_fat]: http://www.ntfs.com/ntfs_vs_fat.htm
[ext4_filesystem]: https://opensource.com/article/18/4/ext4-filesystem
[comparison_file_system]: https://en.wikipedia.org/wiki/Comparison_of_file_systems
[choose_file_system]: https://www.howtogeek.com/howto/33552/htg-explains-which-linux-file-system-should-you-choose/
[swap_web_mit]: http://web.mit.edu/rhel-doc/3/rhel-sag-es-3/ch-swapspace.html
[culturacion_swap]: http://culturacion.com/que-es-una-particion-swap/
[blog_swap]: https://blog.desdelinux.net/que-es-el-swap-en-linux-y-como-utilizarlo/
[hipertextual_swap]: https://hipertextual.com/2015/09/swap-en-linux
[maslinux_swap]: https://maslinux.es/cuanto-swap-deberia-usarse-en-gnu-linux/
[geekytheory_swap]: https://geekytheory.com/es-necesaria-una-particion-swap-en-linux
