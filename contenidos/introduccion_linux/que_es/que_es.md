# ¿Qué es Linux?

:::{figure} tux.png
:align: center
:width: 40%
:::

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

