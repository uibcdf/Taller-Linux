# Reto semanal

El reto de esta semana consiste en resolver los siguientes tres ejercicios. No olvides que los
ficheros y directorios que vas a crear para resolver el reto deben ser empujados a tu clon remoto
en GitHub de tu fork de este repositorio.

## Ejercicio 1

Escribe un script de Bash que automáticamente convierta todos los ficheros 'jpg' presentes en el
directorio en el que se ejecuta a 'png'

### Preparación

Mediante el uso únicamente de la terminal crea un directorio de trabajo con las siguientes instrucciones:

- Crea un nuevo directorio llamado 'solucion_ejercicio_1' y entre en él
- Descarga haciendo uso del comando 'wget' el fichero remoto https://upload.wikimedia.org/wikipedia/en/a/a9/Example.jpg
- Renombra el fichero que obtuviste como 'image.jpg'
- Copia el fichero 'image.jpg' dos veces... la primera como 'imaga.jpg' y la segunda como
  'imago.jpg' en el mismo directorio 'solucion_ejercicio_1'
- Crea un fichero de texto llamado 'image.txt' (puede estar vacío de contenido -recuerdas 'touch'?-).

### Tarea

Escribe un script de bash llamado "conversion_imagenes.sh" que haga lo siguiente:

- Converte todos los ficheros 'jpg' presentes en el mismo directorio donde el script es ejecutado a
  'png'. Para ello tendrás que buscar en internet qué herramienta invocada desde tu script puede
ayudarte (si estás usando Linux... quizá el comando 'convert' del paquete 'imagemagick' pueda
resultarte útil).
- Haz el script ejecutable y ubícalo en el directorio 'solucion_ejercicio_1'

El script debe poder ser ejecutado en la terminal mediante de la siguiente manera:

```bash
./conversion_imagenes.sh
```

Comprueba que efectivamente la ejecución del script produjo los ficheros nuevos: 'image.png',
'imaga.png' e 'imago.png'.

## Ejercicio 2

Escribe un script de bash sencillo para filtrar un fichero de texto.

### Preparación

Encuentra en este directorio un fichero llamado 'enero.txt'. Crea un directorio llamado
'solucion_ejercicio_2' y copia allí dentro el fichero 'enero.txt'. Visualiza el contenido del
fichero con 'less' haciendo uso de la terminal

### Tarea

Escribe un script llamado 'donde_esta.sh' en el directorio 'solucion_ejercicio_2' para hacer lo siguiente:

- El script requiere dos argumentos de entrada:
    - Un nombre ("Ana" o "Lisa")
    - El nombre del fichero de texto que será filtrado
- El script imprime en la terminal con la ayuda del comando 'grep' cada linea del fichero de texto
  que cumple las siguientes dos condiciones:
- El nombre dado como primer argumento del comando está en la linea
- La palabra "Budapest" no está en la linea.

El script debe ser declarado ejecutable para ser ejecutado en la terminal y en el directorio
'solucion_ejercicio_2' de la siguiente manera:
```bash
./donde_esta.sh Ana enero.txt
```

Para encontrar en la pantalla las siguientes lineas como resultado:
```bash
Ana Madrid
Ana Estocolmo
Ana Ciudad de México
```

## Ejercicio 3

Escribe un script de bash para realizar algo de álgebra con los valores encontrados como columnas
en un fichero de texto.

### Preparación

Encuentra en este directorio un fichero llamado 'febrero.txt'. El fichero contiene lineas con
cuatro valores separados por espacios: person, item, price y unit.

Crea un directorio llamado 'solucion_ejercicio_3' y copia allí el fichero 'febrero.txt'

### Tarea

Escribe un script de bash llamado 'obten_total.sh' para hacer los siguiente:

- El script toma two argumentos de entrada por linea de comandos:
    - El nombre de una persona ("Ana" o "Lisa")
    - El nombre del fichero que será filtrado ("febrero.txt")
- Con la ayuda del comando 'awk' lee 'febrero.txt' y escribe un fichero con dos columnas:
    - La primera columna será el nombre del item que aparece en las lineas cuyo primer valor es el
      nombre de la persona dada en el primer argumento de entrada.
    - La segunda columna será el precio total (price x unit) obtenido en las lineas cuyo primer
      valor es el nombre de la persona dada en el primer argumento de entrada.
- El nombre fichero debe llamarse igual que el fichero analizado pero con el prefijo 'total_XXX_'
  donde 'XXX' es el nombre de la persona dada en el primer argumento de entrada.

El script debe tener permisos de ejecución para poder ser ejecutado de la siguiente manera:
```bash
./get_total.sh Lisa febrero.txt
```

El resultado debe ser la creación de un fichero llamado 'total_Lisa_febrero.txt' con el siguiente
contenido:

```bash
Apple 40.0
Banana 160.0
Peach 48.0
```


