<br>
<center>
<img src="https://conda.io/docs/_images/conda_logo.svg" width="40%">
</center>
<br>

# Conda

Esta introducción a Conda está pensada para aquellos que tienen poco o ningún
conocimiento previo. Esperamos pueda serte útil.

## ¿Qué es Conda?

Conda es un gestor de entornos o ambientes de trabajo, paquetes y canales, operativo para varios
lenguages -Python entre ellos-. Antes de nada, aclaremos qué es un paquete, qué
es un canal y qué es un entorno. 


### ¿Qué es un paquete?

Un paquete (o librería) es un conjunto de ficheros de código
'empaquetado' con las instrucciones de instalación pertinentes y programado
para realizar unas tareas específicas. Si estuvíeramos hablando de un lenguage
compilado, el paquete sería el 'programa' junto con su instalador que compilas
(instalas) en tu computadora. Este programa suele requerir para su correcto
funcionamiento que en tu computadora tengas otros programas instalados
-dependencias-. Así, es habitual que antes de instalar un programa tengas que
preocuparte de que las dependencias estén presentes. Por ejemplo, el sistema
operativo Linux cuenta con gestores de paquetes con los que instalas software nuevo en tu
computadora: 'apt-get', 'yum', 'synaptic', 'aptitude', etc -según la distribución que estás
usando-. Estos gestores se preocupan por ti de que el software que quieres instalar encuentre las
dependencias en tu máquina o las descargue del repositorio para su instalación.

Si tuvieras que instalar a mano el software que necesitas y sus dependencias -colocando cada cosa
donde debe ir en tu sistema operativo-... con el paso del tiempo el número de problemas a resolver
para instalar programas nuevos o para que éstos funcionen correctamente haría el mantenimiento de
tu máquina muy laborioso. Es muy conveniente que un gestor mantenga el equilibrio en el ecosistema
de paquetes instalados en tu computadora.

### ¿Qué es un canal?

Un grupo de desarrolladores o usuarios pueden configurar una lista de paquetes
para ser descargados por cualquiera, de manera pública o privada, a través del gestor de paquetes. A este repositorio de
software se le conoce como 'canal'.

Como ejemplo de canal público de conda puedes echarle un ojo a, probablemente, el
canal más popular mantenido por usuarios: [conda-forge][conda_forge] y [su
lista de más de 21,700 paquetes][anaconda_conda_forge].

### ¿Qué es un entorno?

Imagina la siguiente situación:

- Debes instalar la librería 'A' en su última versión 1.2.4 que depende de versiones mayores a la
  2.0.0 de la librería 'B'.
- En tu máquina tienes instalada la versión 1.6.5 de la librería 'B'.
- Las versiones de 'B' mayores que 2.0.0 trabajan con Python 3.9, 3.10 y 3.11. Pero la versión de
  Python que encuentras en tu máquina es la 3.8.

¿Qué puedes hacer? Puedes actualizar la versión de Python de tu sistema operativo a por lo menos la
versión 3.9. Pero tendrás que asegurar que todo el software que ya tienes instalado sea compatible
con la nueva versión de Python, o tendrás que actualizarlo -esperando que para cada programa encuentres un
reemplazo adecuado-. Así, por ejemplo, la librería 'B' se actualizará a una versión mayor que la
2.0.0 para que puedas instalar 'A'. Pero espera un momento... ¿serán el resto de programas que había
en tu máquina haciendo uso de 'B' compatibles con la nueva versión? La situación se complica...

¿Qué te parecería tener una herramienta para crear un entorno, o un ambiente (*environment*), aislado en tu
computadora para instalar la versión 1.2.4 'A' y todas sus dependencias sin afectar al resto de
programas y a tu sistema operativo? Un gestor de entornos o ambientes de trabajo como Conda puede
hacer eso por ti.

Un entorno de 

Tu sistema operativo cuenta probablemente con un interpretador de python
(versión 2.x o 3.x) además de una extensa colección de librerías requeridas por
el mismo sistema o por los programas que instalaste. Cuando desarrollas
software o lo usas a un nivel avanzado, como va a ser el caso, es habitual que
trabajes con librerías experimentales o herramientas que se encuentran siempre
en un eterno proceso de desarrollo y mantenimiento. En este caso es un buen
hábito trabajar con ecosistemas de paquetes (entornos) independientes del
sistema operativo y entre sí. Por ejemplo, puedes crear un entorno con python
2.7 para usar esa librería que todavía no fue actualizada y otro entorno con
python 3.7 para otro tipo de trabajo... y 'cargarlos' y 'descargarlos' como si
fueran microsistemas virtuales independientes.

### ¿Qué es entonces un gestor de entornos, paquetes y canales?

Un gestor de entornos, paquetes y canales, como pueden ser conda, homebrew, pip
o pipenv, se ocupa de administrar tus entornos de trabajo posibilitando en
ellos la instalación y actualización de paquetes desde los canales que
configures.

Conda, creado y soportado por [Anaconda][anaconda], ofrece esto y más. La mejor
manera de comenzar para un usuario inexperto es instalar la última versión de
miniconda y empezar a usarlo.

<br>
<center>
<img src="https://www.explainxkcd.com/wiki/images/c/cb/python_environment.png" width="400">
</center>
<br>

### ¿Qué es Miniconda?

Miniconda es la versión 'mínima' de Conda con la que se aconseja empezar. Conda
ofrece descargar un gestor junto con una gran colección de librerías, pero esto
además de pesado es innecesario. Instala miniconda en tu máquina para comenzar
con el uso de conda y descarga poco a poco los paquetes que vayas requiriendo.

## ¿Cómo se instala?

Puedes encontrar las instrucciones de instalación y manejo de conda en [su
página oficial][conda_docs]. Antes de ver las instrucciones según el sistema
operativo que uses, échale un ojo al menos a la estructura de la [guía de
usuario][guia_conda].

### Linux.

https://conda.io/docs/user-guide/install/linux.html

### MacOS.

https://conda.io/docs/user-guide/install/macos.html

### Windows.

https://conda.io/docs/user-guide/install/windows.html

## ¿Cómo se usa?

Existe una excelente [documentación oficial][conda_docs] con [breves guías para
comenzar][conda_getting_started] y [tutoriales más avanzados][conda_tutorials].

Vamos a exponer aquí la pequeña lista de comandos que más vas a usar.

Cómo actualizar conda:

```python
conda update conda
```

Cómo crear un entorno de python 3 llamado en este caso `academia`:

    
```python
conda create -n academia python=3
```

Cómo cargar o activar un entorno:

```bash
source activate academia
```

Cómo instalar el paquete `numpy`:

```bash
conda install numpy
```

Cómo instalar el paquete `jupyter` del canal `conda-forge`:

```bash
conda install -c conda-forge jupyter
```

Cómo actualizar todos los paquetes de un entorno:

```bash
conda update --all
```

Cómo consultar la lista de paquetes instalados en un entorno:

```bash
conda list
```

Cómo desactivar el entorno cargado:

```bash
source deactivate
```

Cómo consultar la lista de entornos:

```bash
conda info --envs
```

Cómo eliminar un entorno:

```bash
conda remove -n academia
```

Cómo añadir un canal, en este caso `conda-forge`, a la lista de canales
consultados para la instalación y actualización de paquetes:

```
conda config --add channels conda-forge
```

Cómo consultar la lista de canales incluidos en tu archivo de configuración
para instalar y actualizar paquetes, y su prioridad:

```bash
conda config --get
```

Como eliminar un canal, en este caso `conda-forge`, de la lista de canales
incluidos en el archivo de configuración.

```bash
conda config --remove channels conda-forge
```

---

## Dudas, problemas técnicos y soluciones. <a class="anchor" id="dudas"></a>

Para centralizar esas dudas técnicas sobre el tema de esta unidad o proponer
soluciones o sugerencias más técnicas que queremos encontrar en el futuro
comentadas y visibles para todos, haz uso del siguiente canal:

[Foro Técnico: Conda][foro]

## Más recursos útiles <a class="anchor" id="recursos"></a>

Esto era sólo una guia introductoria. No es funcional documentarse o estudiar
mucho sin antes comenzar a usar el sistema operativo Linux. Aprenderás de
manera más solida si con el uso te van surgiendo necesidades a las que vas
dando solución poco a poco. Si la computadora es tu herramienta de trabajo, es
tu deber conocerla. Puedes encontrar -o contribuir añadiendo- más información
útil en el siguiente listado.

### Documentación <a class="anchor" id="documentacion"></a>

https://conda.io/    

### Tutoriales, Webinars y cursos gratuitos <a class="anchor" id="tutoriales"></a>

https://geohackweek.github.io/Introductory/01-conda-tutorial/   \[EN\]    
http://gatomontez.com/articulo/2014/02/16/computo-cientifico-con-python-y-anaconda/#.W-ySQstKiV4   \[ES\]    
https://carpentries-incubator.github.io/introduction-to-conda-for-data-scientists/04-sharing-environments/index.html
https://kaust-vislab.github.io/python-novice-gapminder/00-getting-started-with-conda/index.html
https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-from-an-environment-yml-file

<!---
Alias de enlaces
---!>

[conda_forge]: https://conda-forge.org/
[anaconda_conda_forge]: https://anaconda.org/conda-forge
[anaconda]: https://www.anaconda.com/
[conda_docs]: https://conda.io/docs/
[guia_conda]: https://conda.io/docs/user-guide/index.html
[conda_getting_started]: https://conda.io/docs/user-guide/getting-started.html
[conda_tutorials]: https://conda.io/docs/user-guide/tutorials/index.html
[foro]: https://github.com/uibcdf/Academia/issues/6

