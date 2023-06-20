# Contenido

:::{figure} tux.png
:align: center
:width: 40%
:::

Los siguientes contenidos serán presentados en [una sesión de videoconferencia](sesion.md).
Puedes encontrar en [este enlace](slides/slides.pdf) las slides usadas como soporte.

## ¿Qué es Linux?

Un sistema operativo (SO) es el software que instalas en tu computadora para
gestionar el uso de su hardware (monitor, teclado, procesador, etc.) y que
sirve de plataforma para la instalación de las herramientas que usarás (editor
de texto, editor de imágenes, navegador, etc.). En ese sentido Linux no es un
sistema operativo. Es una familia de sistemas operativos. Todos basados en la
misma tecnología y filosofía de desarrollo, todos descendientes del mismo
sistema madre.

Es relevante entender cómo nace Linux para valorar en lo que se ha convertido,
y así saber qué podemos esperar de él. En la década de los 90, lo que comenzó
en los 60 como un proyecto frustrado -MULTICS- entre el MIT, AT&T Bell Labs y
General electric, cristalizó en un proyecto de sistema operativo casi como un
proyecto académico. En 1970, Ken Thompson, un ingeniero de AT&T que seguía
trabajando por iniciativa propia sobre los rescoldos del sistema operativo
creado para MULTICS, programó un nuevo sistema operativo multitarea con linea
de comandos y unas poquitas aplicaciones: UNICS (más tarde llamado UNIX). Ken
Thompson en realidad sólo pretendía que un juego que Bell Labs había programado
para la computadora del proyecto MULTICS, Space Travel, corriera de manera
rápida y barata. Pero su proyecto acabo siendo empujado por su equipo de
trabajo para crear un sistema operativo de soporte para los desarrolladores de
nuevas aplicaciones de entonces. Años después, en 1985, Richard Stallman crea
la licencia GNU y funda la Free Software Foundation. Richard S. había entendido
que el desarrollo de aplicaciones de uso libre, el acceso a ellas y la
posibilidad de modificarlas y transformarlas, iba a impulsar rápidamente el
progreso científico y tecnológico. En este contexto, en un momento en el que ya
se contaba con varias aplicaciones de uso libre para UNIX y un pequeño grupo de
desarrolladores que apostaban por el acceso libre y la cooperación, Linus
Torvals en 1991 programa un sistema operativo basado en los mismos principios
que UNIX y bajo licencia GNU. Linux, así llamado, nace libre de uso y
desarrollo, con un conjunto de aplicaciones plenamente operativas con las
mismas características y con el potencial de ser modificadas y mejoradas por
cualquiera.

Es así como, desde el comienzo de los 90, Linux comienza en la cabeza y las
manos de varios desarrolladores a generar ramificaciones en forma de distintas
distribuciones. Muchas de ellas respetando el espíritu inicial de la licencia
GNU, de acceso y desarrollo libre. Esto cataliza su uso primero en el entorno
académico para más tarde saltar a la iniciativa privada y el uso doméstico. La
posibilidad para cualquier usuario de actuar de forma activa en el desarrollo:
documentando, reportando fallos, generando soluciones, creando software o
incluso generando nuevas distribuciones de Linux; hace que este proyecto haya
de manera muy rápida resuelto problemas de uso general, como entornos sencillos
y ligeros para el uso de la ofimática, y específicos, como protocolos de
seguridad que hacen de Linux la base para el sistema operativo que opera por
ejemplo en el Departamento de Defensa de Estados Unidos o en el Banco de China.

## ¿Por qué Linux?

Los motivos para usar Linux como SO de trabajo van mucho más allá que una
cuestión de principios. Linux nació como un SO capaz de manejar múltiples
procesos y múltiples usuarios en la misma computadora. Desde entonces ha ido
sofisticándose y adaptándose, gracias a la gran población de
usuario/desarrolladores, para ser eficaz en cuestiones como el cálculo
científico o el análisis masivo de datos. Por ir concretamente a lo que más nos
interesa. Linux es el entorno usado desde su nacimiento en entornos académicos
donde la computación es una herramienta de desarrollo esencial. La manera de
trabajar de Linux nos permite tener todo el control de la máquina de un modo
óptimo en la programación de tareas, aunque esto requiera un esfuerzo de
aprendizaje. Puede que tengas experiencia en el manejo de Windows o MacOS, y
son perfectamente útiles para todas las cuestiones que aprenderás en este
repositorio, pero su diseño original fue hecho para cubrir otras necesidades.
Es cierto que sus entornos de escritorio ya no son la única interfaz de
interacción con la máquina, puedes usar también terminales. Al igual que Linux
incluyó también un entorno gráfico sofisticado para navegar con ventanas. Pero
el desarrollo de aplicaciones de alta demanda computacional se hace, no por
motivos ideológicos, en Linux. A esto podemos añadir que:

- Encontrarás un activo y numeroso grupo de usuarios como tú comentando en
  foros y blogs sus problemas de uso y sus soluciones.
- El aprendizaje de su uso te permite convertirte no sólo en consumidor de
  aplicaciones, sino en generador de tus propias soluciones (que pueden ser
  útiles para los demás también).
- Tiene menos problemas de seguridad que otros SOs.
- Está en constante evolución, dictada por las necesidades de la comunidad, no
  por criterios de mercado.
- La mayoría de distribuciones pueden ser instaladas sin coste alguno. Este es
  el caso de todos los programas y librerías que vas a necesitar a lo largo de
  todas las unidades de UIBCDF-Academia.
- Linux tiene problemas, y más si usas la última versión de ciertas
  distribuciones más experimentales. Pero los desarrolladores o la comunidad de
  usuarios pronto encuentra la solución y ésta es implementada para todos los
  usuarios.

<br>

:::{figure} command_line_fu.png
:align: center
:width: 80%
:::


## Distribuciones de Linux.

Hay infinidad de distribuciones de Linux ([aquí por ejemplo una lista ordenada
por popularidad][distrowatch_popularity]). Pero si Linux es la base común de
estos sistemas operativos, ¿de qué estamos hablando cuando nos referimos a
distribuciones de Linux? Una distribución es un sistema operativo configurado
sobre Linux con cierto grado de personalización y optimización, con una serie
de paquetes de software ajustados entre sí para que el entorno funcione
amigablemente y facilitando una experiencia de uso particular. La distribución
de Linux suele condicionar la forma en que se instala, el entorno de
escritorio, las utilidades de administración y los paquetes más sencillos que
cualquier usuario usa para su gestión. Sin embargo las distribuciones no
limitan ni restringen las utilidades o paquetes a instalar; y la experiencia de
uso a través de la terminal no suele depender de la distribución más que en
unos pocos comandos como por ejemplo la manera en la que instalamos paquetes.
Vamos a hablar de algunas distribuciones para que entiendas a qué nos referimos
con 'distribución' y [cúal se recomienda para cada caso][distrowatch_major].

:::{important}
Los contenidos de este taller no dependen en absoluto de la distribución de
Linux que estés usando o quieras usar. Los comandos y conceptos que aprenderás
en esta unidad, comunes a todas las distribuciones por estar en la esencia del
funcionamiento de Linux.
:::


### Ubuntu

Si es la primera vez que usas Linux para trabajar, [Ubuntu][ubuntu] puede ser
la distribución más adecuada para tu máquina de trabajo (de escritorio o
laptop). Ubuntu lleva años haciendo un esfuerzo por ser una de las
distribuciones más amistosas en su instalación y uso para usuarios no expertos.
Además, puedes encontrar la estabilidad necesaria en sus versiones LTS (Long
Time Stable). El corazón de un sistema operativo Linux, el kernel, se actualiza
constantemente para incluir la compatibilidad necesaria con el nuevo software o
hardware, así como para solucionar problemas de seguridad o adoptar los últimos
protocolos de operabilidad. Es habitual que todos los años se liberen varios
kernels y tengas que actualizar el tuyo para estar 'a la última'. Sin embargo
esto puede generar inestabilidades, ya que caminas siempre en el terreno de la
innovación con herramientas y configuraciones no tan 'testeadas'. Ubuntu libera
dos versiones de su distribución nuevas y actualizadas al año. Y a pesar de que
su vocación es ofrecer un sistema operativo con pocos fallos de uso a usuarios
no expertos, suelen aparecer algunos problemas que a los usuarios de linux con
experiencia no nos parecen graves, pero a un usuario novato pueden generarle
una sensación de inseguridad. Por eso, y para no comprometer máquinas dedicadas
a la producción, hay una versión cada cierto tiempo cuyo mantenimiento y
estabilidad se cuida por encima de las demás: [la versión LTS (Long Time
Stable)][ubuntu_download]. Te aconsejamos que para tu máquina de trabajo, si
eres principiante, instales la última versión LTS de Ubuntu. Afrontarás menos
problemas, disfrutarás de un entorno fácil de configurar y dispondrás de todo
lo necesario para trabajar.

Además, Ubuntu, por ser una de las distribuciones más usadas, cuenta en
internet con un elevado número de blogs y foros donde encontrarás información
sobre todo lo que quieres hacer tanto en español como en inglés.

:::{hint}
Si es la primera vez que vas a usar Linux, y si además te vas atrever a
instalarlo en tu computadora, te recomendamos que uses Ubuntu. Ubuntu es una de
las distribuciones más estables y sencillas en su uso e instalación. Además es
una de las distribuciones más documentadas y cuenta con una gran comunidad de
usuarios que publican en internet dudas, soluciones, tutoriales y demás
información que seguro que encontrarás de utilidad.
:::


### ElementaryOS

Si lo que buscas es algo más estético, sencillo para una primera experiencia de
uso, y que nadie te mire como a un o una nerd: puede que esta sea tu
distribución. En el laboratorio no tenemos experiencia con
[ElementaryOS][elementaryos] y por lo tanto no la recomendamos para un entorno
de producción. Pero últimamente está ganando mucha popularidad y entendemos que
si vienes de MacOs, ElementaryOS te parezca muy agradable.

### Arch

Si lo que buscas es una distribución que venga ligera en su instalación
original y en la que puedas configurarlo todo como un profesional, échale un
ojo a [ArchLinux][archlinux]. Esta distro es para usuarios más experimentados o
para valientes novatos; y para máquinas que requieren un sistema operativo
liviano y ajustable a su hardware, sin artificios ni vistosos procesos poco
útiles.

### CentOS

Gran parte de los servidor y supercomputadores dedicados a cómputo científico
suelen correr con [CentoOS][centoos]. Esta distribución está bien optimizada y
equipada, y es muy estable para este tipo de máquinas. Sin embargo, no es una
distro muy popular para instalar en una laptop de alguien que está comenzando a
usar Linux.

### Pop!\_OS

[System76][system76], además de hacer unos laptops y unas computadoras de
escritorio muy atractivos, han desarrollado una distribución de Linux pensada
para el científico con una estética muy agradable: Pop!\_OS. Si estás buscando
una distribución productiva, no orientada tanto a la ofimática o el uso
doméstico-personal, sino al trabajo computacional intensivo, puede que Pop!\_OS
sea lo que buscas.

### Otras distribuciones

Con el tiempo aprenderás que en el mundo de Linux, las distribuciones son como
los equipos de futbol. Hay razones de todo tipo para ser fan de una u otra.
[LinuxMint][linuxmint] está los últimos años ganando mucho seguidores por
conjugar una buena experiencia de uso para usuarios inexpertos y una larga
colección de paquetes personalizados y versatiles, [Debian][debian] puede que
funcione para perfiles más expertos y nostálgicos (fue el primer sistema
operativo Linux de muchos de nosotros), [RedHat][redhat] es una distro que se
ha especializado en servir para entornos laborales privados con soporte bajo
pago... Y así podemos encontrar personas que nos defiendan con argumentos
plausibles, y pasión, que indudablemente [OpenSUSE][opensuse],
[Fedora][fedora], [Slackware][slackware], [Gentoo][gentoo], [FreeBSD][freebsd]
o [Mandriva][mandriva], son las mejores distribuciones de Linux. 

## ¿Cómo se instala? <a class="anchor" id="Como"></a>

Puede que quieras instalar Linux en una computadora nueva como único sistema
operativo. O puede que quieres en tu computadora disponer de dos sistemas
operativos, Windows y Linux. O quizá no quieres instalar Linux y prefieras
probarlo antes desde una USB booteable sin alterar lo que tienes en tu máquina.
O si tienes Windows 10 u 11, seguramente te va a parecer más sencillo probar
Linux instalando Ubuntu como si fuera un programa más de tu máquina

Sea cual sea tu caso, encontrarás información sobre cómo puedes instalar Linux
(específicamente Ubuntu), probarlo y/o trabajar con él, en la página ["Como
instalar y/o trabajar con Linux" del Material Suplementario del Taller](../material_suplementario/linux/linux.md).

:::{importante}
Si quieres instalar una distribución de Linux, nada mejor que acudir a su
documentación oficial para encontrar una buena guía sobre el proceso de instalación.
:::

:::{hint}
Puedes probar Ubuntu antes de instalarlo en tu máquina. Sólo necesitas una
memoria USB o un DVD para crear un sistema operativo 'externo' con el que
puedes arrancar cualquier máquina -y probar la distribución-.
O puedes, si tienes Windows 10 u 11, instalar Ubuntu en tu sesión de Windows
como si fuera un programa más.
:::

## ¿Qué es el kernel?

El kernel de Linux es el elemento principal del sistema operativo Linux. Es el nucleo del sistema operativo encargado de:

- La gestión de los procesos.
- La gestión de la memoria.
- Comunicación con los componentes internos de la computadora y sus periféricos.
- La comunicación entre el software instalado en la máquina.
- La seguridad de tu sistema operativo.

Las primeras versiones del kernel de Linux se remontan a 1991, pero la que
usarás en tu distribución tiene ya poco que ver con esas.

Con respecto al kernel, como usuario, no interaccionarás. Y como administrador,
debes saber que cada poco tiempo (a veces cada pocas semanas) se publican
versiones nuevas que debes de considerar por motivos de seguridad. No tengas
reparo en actualizar con frecuencia el kernel de tu máquina: estos harán que tu
máquina sea más estable y segura.


## Entornos de escritorio.

Si estás aproximándote a Linux desde hace poco es posible que confundas los
entornos de escritorio con las distribuciones. El entorno de escritorio es la
parte más visible de la distribución y lo primero con lo que probablemente vas
a interaccionar: el escritorio, la barra superior, el menú desplegable, el
docker, las ventanas, etc. Hay entornos de escritorio tradicionales, tan
populares como sólidos, como son [Gnome](https://www.gnome.org/) ([proyecto
fundado por los
mexicanos](https://www.xataka.com.mx/aplicaciones/miguel-de-icaza-y-federico-mena-los-padres-mexicanos-del-proyecto-gnome-uno-de-los-entornos-de-escritorio-mas-famosos-de-linux)
[Miguel de Icaza](https://en.wikipedia.org/wiki/Miguel_de_Icaza) y [Federico
Mena](https://es.wikipedia.org/wiki/Federico_Mena)) o
[KDE](https://www.kde.org/), y otros más novedosos y vistosos como
[Pantheon](https://www.fosslinux.com/4652/pantheon-everything-you-need-to-know-about-the-elementary-os-desktop.htm/),
o ligeros y sencillos como [XFCE](https://www.xfce.org/). Aunque las
distribuciones apuestan por que uno u otro venga instalado por defecto, y a
veces desarrollan su propio entorno de escritorio (como hizo Ubuntu con
[Unity](https://unity8.io/) o Elementary con Pantheon), casi todos los entornos
de escritorio pueden ser instalados en cualquier distribución. Es por esto que
no debería de condicionar tu elección de distribución, puedes [instalar
Pantheon en
Ubuntu](https://www.maketecheasier.com/install-run-pantheon-desktop-ubuntu/) o
descargar [KUbuntu -Ubuntu con KDE-](https://kubuntu.org/), aunque por defecto
ahora venga con GNOME.

## ¿Qué es la terminal?

Probablemente estés habituado/a a interaccionar con tu computadora a través del
entorno gráfico de escritorio. Resulta muy intuitivo y casi no requiere proceso
de aprendizaje, pero consume muchos recursos y es altamente ineficiente cuando
la computadora es tu herramienta para algo más que el uso de una o dos
herramientas de ofimática.

La terminal es esa ventanita monocolor que sólo contiene texto y cuya última
linea siempre acaba con un cursor parpadeante que puede resultar al principio
intimidante... ya que aparece y desaparece intermitentemente como diciendote:
¿y ahora qué? Pues bien, efectivamente es la puerta de entrada a la interacción
con tu máquina. El cursor espera comandos, y esa lista de comandos que entiende
son un lenguage, con sus reglas sintácticas, que debes aprender para
comunicarte con tu máquina. El lenguage que puebla por defecto la mayoría de
los sistemas Linux se llama Bash. ¿Es el único? No, hay otros lenguajes para la
terminal más sofisticados como Zsh o Fish, pero Bash es el interpretador más
común y el que únicamente usarás a lo largo de tu vida si no es que eres una
persona muy curiosa o alcanzas un nivel de experiencia como para encontrar los
límites e incomodidades del uso de Bash.

## ¿Qué es el prompt?

Antes de hablar de qué vamos a escribir en la terminal, hagamos un breve
comentario sobre lo que precede al cursor en la terminal. Ese fragmento de
texto que no desaparece por mucho que le demos a la tecla 'entrar' se llama
'prompt'. Es perfectamente configurable y personalizable y habitualmente suele
contener el nombre del usuario que está operando la terminal, el nombre de la
máquina precedido del símbolo '@' (muy util cuando en la misma terminal hacemos
conexiones remotas con otras máquinas) y por último la dirección o 'path' del
archivo en el que nos encontramos en la terminal. Esto nos lleva otro concepto
que usaremos como punto de inicio en nuestro aprendizaje de Bash: la navegación
de ficheros.

## ¿Qué es Bash?

Bash es el interpretador más usado en los sistemas operativos Linux. ¿Qué
significa que sea el interpretador? Sencillo, en la terminal escribirás
comandos e instrucciones que un programa que forma parte de tu sistema
operativo leerá, interpretará y ejecutará: ese es Bash. Y por extensión, el
lenguaje que entiende lo llamamos 'bash'. Este lenguaje te servirá para
interaccionar con tu computadora mediante la terminal, así como para escribir
scripts.

La mayor parte del contenido de este taller pretende enseñarte la sintaxis de
bash para que puedas hacer uso eficientemente de la terminal como usuario y/o
como administrador.

:::{note}
Si eres usuario de macOS y la versión que usas es posterior a la versión 10.15,
seguramente el interpretador de tu máquina no es Bash, es Zsh. No te preocupes,
la sintaxis más básica está heredada de Bash. Puedes seguir el taller
perfectamente. Cuando haya alguna diferencia no nos olvidaremos de ti, haremos las precisiones necesarias.
:::

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

