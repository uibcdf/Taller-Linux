# Cómo instalar y/o trabajar con Linux

Posiblemente quieres probar Linux y aprender a usarlo pero no te atreves a
instalarlo en tu máquina. Puede que ya hayas pasado esa etapa, o que estés
decidido a probarlo de veras, y quieras instalar una distribución de Linux
aunque... todavía no tienes la confianza como para abandonar tu sistema
operativo Windows. O por último, quizá has decidido ser valiente y tienes
planeado instalar en tu máquina Linux como sistema operativo único. Sea cual
sea tu situación, encontrarás en esta página indicaciones para poder proceder.

Comencemos pensando en que estás descubriendo este sistema operativo y quieres
probarlo y aprender sin todavía modificar nada en tu computadora. Si este es tu
caso, visita la sección ["No quiero instalar Linux todavía"](no_quiero_instalar).

Si por el contrario quieres ya instalar una distrución de Linux en tu máquina,
sóla o acompañada de otros sistemas operativos, visita la sección ["Quiero instalar Linux"](quiero_instalar).

(no_quiero_instalar)=
## No quiero instalar Linux todavía

Si quieres probar, aprender y practicar el uso de un sistema operativo Linux y
no quieres, o no puedes, hacer ninguna modificación en tu computadora... tienes muchas opciones.

```{admonition} Recomendación
:class: tip

Nuestra recomendación para comenzar a interaccionar con una distribución de
Linux en cualquier máquina, sin instalar nada, es el uso de Ubuntu en una USB
booteable. Sin emargo, si tienes instalado en tu computadora un sistema
operativo Windows 10 o Windows 11, hay una opción más sencilla para ti: usar
Ubuntu como un programa más dentro de Windows.

```

### Simuladores o servidores remotos en la web

Simplemente haciendo uso de tu navegador, puedes acceder a simuladores o
servidores remotos disponibles en internet. Estas webs pueden desde dejarte
practicar el lenguaje de la terminal (usualmente Bash) hasta permitirte operar
con una máquina virtual o remota.

```{note}

Esta subsección está mostrada aquí únicamente para que sepas que existe esta
opción. Te sugerimos que la explores, pero no consideramos que pueda ser de
utilidad para realizar este taller.

```

A continuación te ofrecemos las ligas a algunos de ellos:

- [WebVM.io](https://webvm.io/)
- [masswerk.at](https://www.masswerk.at/jsuix/index.html)
- [bellard.org/jslinux/](https://bellard.org/jslinux/)
- [copy.sh/v86/](http://copy.sh/v86/?profile=linux26)
- [linuxcontainers.org/lxd](https://linuxcontainers.org/lxd/try-it/)
- [copy.sh](http://copy.sh/v86/?profile=linux26)
- [Webminal](https://www.webminal.org/)
- [Cocalc](https://cocalc.com/features/terminal)
- [Domsignal Bash Online Compiler](https://domsignal.com/bash-online-compiler)
- [tutorialspoint.com/linux\_terminal\_online](https://www.tutorialspoint.com/linux_terminal_online.php)

Estos simuladores o servidores en la red pueden ser la herramienta perfecta
para comenzar a explorar el uso de la terminal. Pero puede que sólo quieras
practicar tus conocimientos de programación en Bash con un editor en linea:

- [LeetCode](https://leetcode.com/playground/new/empty?ref=itsfoss.com)
- [tutorialspoint.com/execute\_bash\_online](https://www.tutorialspoint.com/execute_bash_online.php?ref=itsfoss.com)
- [JDoodle bash online tester](https://www.jdoodle.com/test-bash-shell-script-online/?ref=itsfoss.com)
- [Paiza.io bash online](https://paiza.io/en/projects/new?language=bash)
- [ShellCheck](https://www.shellcheck.net/)
- [RexTester](https://rextester.com/l/bash_online_compiler)
- [LearnShell](https://www.learnshell.org/)
- [Codeanywhere](https://codeanywhere.com/languages/bash)
- [myCompiler](https://www.mycompiler.io/new/bash)
- [OnlineGDB](https://www.onlinegdb.com/online_bash_shell)

Si buscas tener una experiencia más próxima a usar una distribución de Linux y
no sólamente la terminal, existen otras opciones. Por ejemplo, el siguiente
enlace te ofrece la posibilidad de usar algunas distribuciones desde tu navegador:

- [onworks.net](https://www.onworks.net/)

### Ubuntu como un programa más en Windows

La distribución de Linux Ubuntu es una de las más estables y sencillas para
comenzar. Los desarrolladores de Canonical -empresa que desarrolla Ubuntu-
llevan años trabajando para llegar a cualquier tipo de usuario sin importar su
grado de destreza en el uso de una computadora. Es por eso que ofrecen dos
posibilidades para usar su distribución sin necesidad de ser instalada: como
usb booteable o como programa dentro de tu sesión de Windows.

Si usas Windows 10 o Windows 11, esta opción puede ser muy conveniente para
empezar a usar una distribución de Linux casi como si fuera el sistema nativo
de tu máquina. Puedes correr a [instalar Ubuntu desde Microsoft
Store](https://apps.microsoft.com/store/detail/ubuntu/9PDXGNCFSCZV) o consultar
primero la documentación oficial:

- [Ubuntu: Ubuntu on WSL2](https://ubuntu.com/tutorials/install-ubuntu-on-wsl2-on-windows-11-with-gui-support#1-overview)
- [Microsoft: Install Linux on Windows with WSL](https://learn.microsoft.com/en-us/windows/wsl/install)

También puedes usar tu buscador para explorar qué webs te pueden orientar en el proceso de instalar Ubuntu en Windows:

- [linuxhint.com/wsl](https://linuxhint.com/install_ubuntu_windows_10_wsl/)
- [windows101tricks.com](https://windows101tricks.com/run-ubuntu-on-windows-10/)
- [linuxhint.com/windows-store](https://linuxhint.com/install-ubuntu-windows-from-windows-store/)

### Sistemas operativos virtuales

Imagina que puedes abrir Ubuntu desde tu sistema operativo MacOs o Windows como si
fuera una aplicación más. O al revés, que sobre tu distribución de Linux pudieras
abrir y cerrar una sesión en Windows u otro sistema operativo como si fuera un
programa más. Esto es lo que posibilitan la instalación de máquinas virtuales
como [VirtualBox][virtualbox](https://www.virtualbox.org/) de Oracle
-gratuito-. Esta máquina virtual la puedes instalar en tu sistema operativo y
crear computadoras virtuales con un espacio de disco duro asignado y con una
gestión del hardware de tu computadora independiente a la que realizará tu SO
de soporte. Si nunca has usado Linux, esta también puede ser una buena manera para
comenzar asumiendo poco riesgo: puedes aprender a usar una distribución como
Ubuntu como si fuera una ventana más abierta en tu escritorio. 

### Ubuntu en una usb booteable

Como mencionamos anteriormente, Ubuntu puedes ser una muy buena distribución de
Linux para usuarios nuevos. Ubuntu es sencillo, estable y está muy bien
documentado. Además, gracias a que es una de las distribuciones más usadas es
fácil resolver dudas o problemas gracias a los miles de usuarios que participan
en foros o escriben tutoriales.

Para probar ubuntu existe un mecanismo muy recomendable por ser nada invasivo: la usb booteable.
Esta opción puede servir para probar Ubuntu en cualquier máquina independientemente del sistema operativo que use.

¿Qué es una usb booteable? Tu computadora, cuando la prendes o enciendes, lo
primero que hace es buscar un sistema operativo e iniciarlo. Casi con toda
seguridad podemos afirmar que en la máquina que usas diariamente, ese sistema
operativo se encuentra en su disco duro (uno de sus discos duros, si tienes más
de uno). Pero, ¿qué pasaría si ponemos un sistema operativo Linux en una usb y
le decimos a tu máquina que inicie con él? No hace falta que imagines mucho, lo
puedes probar. Ubuntu te indica paso a paso como crear una usb booteable para
ser cargado y usado en tu computadora sin necesidad de alterar para nada lo que
ya tienes instalado en ella. Échale un ojo a la documentación oficial, sólo
debes seguir sus pasos:

- [Cómo crear una USB booteable desde Windows](https://ubuntu.com/tutorials/create-a-usb-stick-on-windows#1-overview)
- [Cómo crear una USB booteable desde Mac](https://ubuntu.com/tutorials/create-a-usb-stick-on-macos#1-overview)
- [Cómo crear una USB booteable desde Ubuntu](https://ubuntu.com/tutorials/create-a-usb-stick-on-ubuntu#1-overview)

(quiero_instalar)=
## Quiero instalar Linux

<div class="alert alert-success" role="alert"> <strong>Ayuda:</strong> Si
quieres instalar Ubuntu, nada mejor que acudir a la documentación oficial para
encontrar una buena <a
href='https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview'>guía de
cómo se instala la versión para computadoras personales</a> o <a
href='https://ubuntu.com/tutorials/install-ubuntu-server#1-overview'>la versión
para servidores</a> (en esta última puedes encontrar orientación sobre la
configuración de particiones). </div>

<div class="alert alert-info" role="alert"> <strong>Sugerencia:</strong> Si
quieres, puedes probar Ubuntu antes de instalarlo en tu máquina. Sólo necesitas
una memoria USB o un DVD para crear un sistema operativo 'externo' con el que
puedes arrancar cualquier máquina -y probar la distribución-. Encuentra las
instrucciones en <a
href='https://ubuntu.com/tutorials/try-ubuntu-before-you-install#1-getting-started'>este
enlace</a>. </div>

Si es la primera vez que usas Linux, has de saber que cada distribución tiene
su instalador. No hay un protocolo único de instalación para todo Linux. Puedes
encontrar instaladores muy sencillos, con poco margen para personalizar la
configuración, o muy completos pero complicados para un usuario inexperto. Es
recomendable entonces que para empezar elijas una distribución amigable, bien
documentada y con un buen grado de popularidad. El proceso que aquí vamos a
describir es únicamente una descripción sobre la toma de decisiones que has de
hacer, eso sí es común a cualquier instalación. Tomaremos el ejemplo de querer
instalar Ubuntu como caso práctico para introducir los comentarios a esas
decisiones. Si tu intención es instalar otra distribución, seguramente tras
leer esta sección y acudir a la documentación web correspondiente, encuentres
el proceso más sencillo. 

### Búsqueda de documentación

Lo primero que debes hacer es una búsqueda de la documentación que te oriente
sobre el proceso de instalación de la distribución que deseas. En el caso de
Ubuntu es fácil llegar tras una búsqueda rápida a abrir en el navegador páginas
como las siguientes:

https://www.ubuntu.com/download/desktop
https://tutorials.ubuntu.com/tutorial/tutorial-install-ubuntu-desktop#0
https://www.muylinux.com/2018/06/18/guia-instalacion-ubuntu-18-04-lts/
https://www.muylinux.com/2018/05/29/instalar-ubuntu-consideraciones-previas/
https://es.wikihow.com/instalar-Ubuntu
https://www.genbeta.com/paso-a-paso/linux-paso-a-paso-instalar-ubuntu-con-dual-boot-junto-a-windows-10
https://www.sololinux.es/que-hacer-despues-de-instalar-ubuntu-18-04-bionic-beaver/
https://www.genbeta.com/a-fondo/8-cosas-y-algun-extra-que-hacer-luego-de-instalar-ubuntu-18-04
https://maslinux.es/15-cosas-que-hacer-despues-de-instalar-ubuntu-18-04-bionic-beaver/
https://www.linuxadictos.com/9-cosas-que-hacer-despues-de-instalar-ubuntu-18-04.html   

Como verás hay infinidad de foros, blogs y documentación que puedes encontrar.
Échales un ojo antes de ponerte manos a la obra.

### ¿USB booteable o CD para la instalación?

Uno de los primeros pasos para instalar cualquier distribución de Linux es
descargar el SO y su instalador. Estos habitualmente vienen en forma de único
fichero '.iso' para quemar un CD o DVD, y guardarlo como soporte de
instalación. Pero hoy en día muchas computadoras ya no cuentan con lector de CD
o DVD. Es mejor idea descargar la distribución de Linux para su instalación en
un USB. Esto no es sin más descargar el instalador y copiarlo en tu USB. Hay
que hacer que en la memoria USB se genere un pequeño sistema Linux para que
cualquier computadora pueda arrancar sin necesidad de sistema operativo propio.
Es lo que se llama hacer un USB booteable (que sirve para hacer *boot*). Esta
opción tiene, además de servir como dispositivo de instalación, otras dos
ventajas:

- Te va a permitir probar la distribución de Linux con tu computadora sin
  necesidad de instalar nada. En el caso de Ubuntu, puedes conocer sobre esta
  posibilidad [aquí][try_ubuntu_before_install].
- Te permite disponer de un sistema operativo de auxilio en el caso de tener
  que diagnosticar, reparar, recuperar o reinstalar el SO de tu computadora.

En el caso de Ubuntu, el proceso para hacer un USB booteable de instalación
está bien documentado. Es uno de los primeros pasos a dar en cualquier
documentación que encuentres: ver el [proceso de instalación
aquí][tutorial_install_ubuntu_desktop], o [la creación del usb booteable
aquí][tutorial_usb_booteable].

Para usar el USB booteable debes tenerlo enchufado a la computadora antes de
encenderla. Muy probablemente la bios de tu máquina esté configurada para darle
prioridad al SO encontrado en un USB antes que a los ubicados en el disco duro.
Si es así, el instalador te guiará enseguida y podrás comenzar el proceso. Si
no, debes modificar el orden de prioridad de los dispositivos de arranque en la
bios o acceder a las opciones del menú de arranque de tu máquina, ya que
habitualmente el fabricante habilita la posibilidad de iniciar desde el USB sin
modificar la configuración de manera permanente.

En el caso de Ubuntu, lo primero que verás al arrancar con el USB será una
ventana que te permite decidir entre probar Ubuntu o instalarlo:

<center><img src="https://i.stack.imgur.com/pNTOi.png" width="30%"></center>

Si decides instalarlo, el proceso es guiado y sencillo. El mismo instalador te
orientará en la toma de decisiones. Puede que la única decisión sobre la que
necesites un poco de información es la creación de particiones.

### ¿Particiones?

Con respecto a la máquina sobre la que vas a hacer la instalación, casi la
única decisión que debes tomar es si vas a hacer particiones en el disco duro,
cúales y para qué. Una partición es un sector del disco duro que va a funcionar
como volumen estanco e independiente. Estarás pensando: ¿como si fuera un nuevo
disco dentro del disco duro? Si, exactamente así. Y puedes generar varias
particiones. Podrías por ejemplo sobre el mismo disco instalar Windows y varias
distribuciones de Linux, y decidir en el momento de arrancar la computadora qué
sistema y partición quieres usar. O podrías, por ejemplo, decidir una política
de cuotas de disco para algunas de tus carpetas de Linux creando, por poner un
caso, un volumen de tamaño fijo para el directorio llamado 'home' y otro para
'opt', que no sea ocupado por otros directorios. Las posibilidades son muy
diversas, pero nos centraremos aquí en el caso de que estés haciendo una
sencilla instalación en tu computadora de trabajo. Puedes entonces encontrarte
en uno de los siguientes escenarios.

#### Tengo Windows instalado y quiero además usar Linux.

Posiblemente tu máquina venía con un sistema Windows. Puede que quieras usarlo,
además del Linux que vas a instalar. Para esto puedes comenzar el proceso de
instalación de Linux con Windows en tu disco duro. Este proceso guiado te
comunicará en un determinado momento que se detectó otro sistema operativo y te
ofrecerá la opción de instalar únicamente Linux, borrando todos los datos que
hasta entonces se encuentran en tu computadora, o instalar Linux junto con
Windows (en otra partición). En el caso de Ubuntu, la correspondiente pantalla
del instalador se ve así:

<center><img src="Install-Ubuntu-Alongside-With-Windows.png"
width="400"></center>

Debes elegir la primera opción, 'Install Ubuntu alongside Windows boot
manager'.

<div class="alert alert-info" role="alert"> <strong>Sugerencia:</strong> Hoy en
día puedes instalar la terminal de Ubuntu dentro de Windows 10 como si fuera
una aplicación más. Puede que antes de instalar Ubuntu, quieres probar está
opción en tu Windows 10. Échale un ojo a la documentación oficial de Ubuntu
para descubrir cómo puedes hacerlo en <a
href='https://ubuntu.com/tutorials/ubuntu-on-windows#1-overview'>este
enlace</a>. </div>

#### Tengo Windows instalado pero sólo quiero usar Linux.

En este caso puedes, arrancando la computadora con el USB booteable,
reformatear el disco duro para dejarlo limpio antes de la instalación. O puedes
comenzar el proceso guiado con Windows en tu disco duro. Este proceso te
comunicará en un determinado momento que se detectó otro sistema operativo y te
ofrecerá la opción de instalar únicamente Linux borrando todos los datos que
hasta entonces se encuentran en tu computadora (haz copia de seguridad de todo
lo que quieres guardar antes de la instalación). En el caso de Ubuntu, la
correspondiente pantalla del instalador es como la imagen de la subsección
anterior, y debes elegir la segunda opción: 'Erase disk and Install Ubuntu'.

#### Mi máquina no tiene SO y quiero usar sólo Linux.

Este puede ser el caso más sencillo. Arranca la computadora con el USB
booteable e inicia el proceso de instalación. Llegado el momento verás que
tienes la opción de hacer una instalación únicamente de Linux sobre todo tu
disco duro. En este caso el instalador tomará las decisiones de cómo
reformatear y particionar el disco. Si estás instalando Ubuntu, esto es lo que
verás:

<center><img src="erase-disk-and-install-ubuntu.png" width="400"></center>

Como se indica en la imagen, elige la opción que dice "Erase disk and install
Ubuntu". Y continua el proceso de instalación guiada.

#### Mi máquina no tiene SO y quiero usar más de uno.

Lo primero en esta circunstancia es decidir cúanto espacio de disco duro vas a
dedicar a cada SO. Además, si lo que quieres es instalar varias distribuciones
de Linux, puedes tambien tomar la decisión de compartir particiones. Supongamos
que quieres la carpeta 'Proyectos' como una única partición visible para tus
distribuciones de Linux, por ejemplo. Lo puedes hacer. Pero aquí supondré que
quieres instalar otro sistema operativo, como Windows, y hay que dejarle
espacio. En este caso vas a tener que optar por definir manualmente tu esquema
de particionado para instalar. En la imagen mostrada en la subsección anterior,
haz click en "Something else". Aparecerá una ventana como la siguiente en la
que decidir el tamaño y ubicación de las particiones:

<center><img src="https://i.stack.imgur.com/3DBJC.png" width="400"></center>

El proceso lo vas a encontrar muy bien documentado en webs como por ejemplo
[esta][installation_guide_blog]. Vamos a mencionar aquí alguna cosa:

- Es recomendable que hagas una partición para el directorio 'boot'. Medio giga
  de memoria está más que bien para una gestión cómoda de una computadora
  personal.
- Hacer una partición para '/home' también puede ser buena idea, aunque no
  necesario. Tener el resto en su propia partición puede evitar disgustos al
  ocupar mucho espacio con tus cosas no dejando espacio para el sistema.
- Puedes hacer una partición para todos los directorios, o los directorios
  restantes, designandola como punto de anclaje de '/'.
- Aunque ya no es muy necesaria, todavía debemos definir una partición de
  memoria auxiliar de intercambio *swap*. Existen guías y criterios para
  definir su tamaño, pero como regla del pulgar podemos elegir la misma
  cantidad de memoria que tenemos de RAM.

El último concepto, la memoria swap, merece a continuación un párrafo ya que
será una partición con la que no vas a interaccionar explícitamente. Pero antes
verás que para crear una partición, además de su tamaño, debes elegir la
naturaleza de su gestión de ficheros.

### El sistema de ficheros.

[Qué es el *journaling* o el *journal file system*][journaling] es algo que
escapa a los objetivos de esta unidad. Puedes buscar información para
comprender los detalles. Es recomendable que alguna vez lo hagas. Pero para
poder culminar el proceso de instalación correctamente debes saber que existen
distintas estrategias de gestión de ficheros en disco que pueden condicionar su
uso. [Desde finales de los 70 y hasta los 90 Dos y Windows manejaban el sistema
FAT (FAT12, FAT16 y FAT32)][fat_allocation_table]. Su origen estaba motivado
por cómo indexar la organización de ficheros en un disco *floppy* blando (y
grande). Te puedes imaginar que a medida que los ficheros crecían en tamaño y
los soportes en capacidad de memoria, hubo que diseñar nuevas estrategias.
[FAT12 tenía una limitación de tamaño máximo de partición de 32 MB, FAT16 ya
permitía un tamaño máximo de fichero de 2GB y FAT 32 de 4GTB][ntfs_vs_fat]. Hoy
día Windows maneja un protolo llamado NTFS que permite gestionar ficheros de
tamaño máximo 16TB -por hablar de algo que nos puede afectar directamente-. Sin
embargo Linux adoptó desde el principio otro tipo de estrategias, [desde EXT2 a
comienzos de los 90 hasta el día de hoy en el que la mayoría de distribuciones
para computadora de escritorio hacen uso de EXT4][ext4_filesystem] ([aunque
existen otros tipos de sistemas de fichero que pueden adoptar las computadoras
de cálculo intensivo o los servidores][comparison_file_system]).

Dicho esto, te preguntarás: Bien, ¿Pero qué sistema debo de elegir cuando creo
las particiones? [En caso de duda, y para un uso común, la mejor opción ahora
mismo es EXT4 para todas tus particiones de Liinux (menos la de memoria
swap)][choose_file_system].

### La memoria Swap.

En Linux, desde las primeras distribuciones, se recomienda generar una
partición de disco duro que se usará como area de intercambio temporal en el
caso de que la memoria RAM se haya ocupado. Se llama memoria Swap. Obviamente
el uso del disco duro para memoria de ejecución de procesos es algo muy lento,
pero efectivo en caso de rescate. Si estás trabajando con un disco de estado
sólido, el escenario cambia, ya que es de lectura y escritura mucho más rápida.
Pero si no, cuando tengas muchas aplicaciones abiertas o estés ejecutando un
programa que requiera un gran manejo de datos en memoria, notarás, si la
memoria RAM se agota, como la computadora se vuelve muuuuy lenta... no se
colgará, pero se vuelve extremadamente lenta mientras migra ciertos datos de la
memoria RAM a la Swap. Esta situación entonces no es del todo catastrófica, te
dejará margen para que elimines el proceso que aumentó el consumo. Después,
suele tardar un tiempo en recuperar el comportamiento normal y puede que por el
camino haya algún proceso dando mensajes de que no responde. Puedes leer un
poco más sobre la swap [aquí][hipertextual_swap], [aquí][blog_swap],
[aquí][culturacion_swap] o [aquí][web_mit_swap].

[¿Cúanta memoria entonces tienes que dedicar a tu Swap?][maslinux_swap] No hay
una respuesta clara. También podemos [preguntarnos si efectivamente esta
memoria es necesaria cuando ya la RAM que tienes en la computadora tiene un
tamaño razonable][geekytheory_swap]. El consejo que podemos dar es que si
tienes un disco duro de más de 1 Tera, no te va a hacer daño crear una
partición Swap, y el tamaño puede ser entre una y dos veces la cantidad de
memoria RAM que tienes. En nuestro caso, en las laptops tenemos 8 GB de RAM y
una Swap de otros 8 GB, y para el uso que le damos es suficiente. En las
computadora de escritorio tenemos 64 GB de RAM y 16 GB de Swap, aunque más de 8
GB de Swap puede ser innecesario, ya que la usamos para hacer cálculos más
demandantes y preferimos prevenir.

## ¿Puedo usar además otros sistemas operativos en la misma máquina?

Hemos mencionado en la sección anterior que sí es posible instalar en el mismo
disco duro, en particiones distintas, Linux junto con otros sistemas operativos
(u otras distribuciones de Linux). Al iniciar la computadora, un menú te dará
la opción de elegir con qué sistema operativo quieres trabajar. La desventaja
quizá puede ser que para ejectuar una aplicación que tienes en tu partición de
Windows, por ejemplo, debes de cerrar tu sesión en Ubuntu y reiniciar la
máquina. No es tan cómodo pasar de uno a otro si sólo es para cuestiones
puntuales y sencillas. Para simultanear sobre la misma sesión de tu computadora
varios sistemas operativos, existe otra opción: los sistemas operativos
virtuales.

### Sistemas operativos virtuales.

Imagina que puedes abrir Ubuntu desde tu sistema operativo Windows como si
fuera una aplicación más. O al revés, que sobre tu distribución de Linux puedes
abrir y cerrar una sesión en Windows u otro sistema operativo como si fuera un
programa más. Esto es lo que posibilitan la instalación de máquinas virtuales
como [VirtualBox][virtualbox](https://www.virtualbox.org/) de Oracle
-gratuito-. Esta máquina virtual la puedes instalar en tu sistema operativo y
crear computadoras virtuales con un espacio de disco duro asignado y con una
gestión del hardware de tu computadora independiente a la que realizará tu SO
de soporte. Si nunca has usado Linux, esta puede ser una buena manera para
comenzar asumiendo poco riesgo: puedes aprender a usar una distribución como
Ubuntu como si fuera una ventana más abierta en tu escritorio. 

### Compatibilidad de ficheros.

Otro inconveniente similar al mencionado anteriormente, puede ser el acceso a
ficheros en particiones de sistemas distintos. Supongamos que tienes una
partición en Linux y otra en Windows. Imagina que trabajando en Linux, con
todas tus terminales y aplicaciones abiertas, necesitas acceder a la
información de un archivo de la partición en Windows. ¿Tienes que cerrar tus
aplicaciones, reiniciar en Windows, leer el fichero, y volver a Linux? Puede
que te parezca acertada esa suposición pensando además que ambas particiones
fueron formateadas con sistemas de ficheros distintos, seguramente EXT4 y NTFS.
Pero no, no es necesario. Linux puede acceder a otros volúmenes con otros
sistemas de ficheros. Así puedes "montar" tu volumen de Windows y tener acceso
al menos seguramente para lectura. Y si dicho volumen fue formateado en otro
sistema como vFAT32, es posible también escribir. Puedes checar qué sistema de
ficheros puede ser leido y/o escrito desde qué sistema operativo en la tabla
denominada "OS support" en [la comparación reportada en
Wikipedia](https://en.wikipedia.org/wiki/Comparison_of_file_systems).

### Usando una memoria usb compatible con distintos SOs.

Si leiste la sección anterior entenderás entonces que si vas a formatear una
memoria USB para uso indistintamente en Linux, Windows y MacOS, no sirve
hacerlo en cualquier sistema de ficheros. Puedes encontrar [tablas en internet
en las que consultar qué formato debe tener tu memoria USB para ser leida con
los sistemas operativos que
trabajas](https://www.7dayshop.com/blog/operating-systems-and-file-systems-cross-compatibility-windows-apple-linux-playstation-xbox-android/).
En principio, tu memoria de 16 o 32 Gb para ser usada sin problema en los tres
SOs anteriormente citados, debería ser formateada como FAT32.

