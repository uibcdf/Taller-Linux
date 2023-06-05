# Reto semanal

El reto de esta semana consiste en resolver los siguientes tres ejercicios. No olvides que los
ficheros y directorios que vas a crear para resolver el reto deben ser empujados a tu clon remoto
en GitHub de tu fork de este repositorio.

## Ejercicio 1

Escribe un script de bash para realizar algo de álgebra con los valores encontrados como columnas
en un fichero de texto.

### Preparación

Encuentra en este directorio un fichero llamado 'febrero.txt'. El fichero contiene lineas con
cuatro valores separados por espacios: person, item, price y unit.

Crea un directorio llamado 'solucion_ejercicio_1' y copia allí el fichero 'febrero.txt'

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

## Ejercicio 2

At the end of this exercise, you wil have your own command "find\_and\_replace" to be used by your
user no matter whats the working dir in your terminal.

Write a script to find and replace a given string ('text pattern') in all files located in the directory where
the script is executed -including those files inside directories found in the same working dir-.

### Preparation

Find the directory "sandbox" and have a look to its content.

Calculate in the file "sandbox/C/lorem.py" the number of "et" words over the total number of words
in the file. You can find some help in the commands "wc", "grep" or "less".

### Task 1

Write a script to find and replace a given string ('text pattern') in all files located in the directory where
the script is executed -including those files inside directories found in the same working dir-.


Let's call the bash script "find\_and\_replace" and write its lines according to the following
indications:
   - The script has to be executed in the terminal.
   - The script takes two arguments via command line: string\_A and string\_B.
   - Using the commands "find" and "sed", the script looks for occurrences of string "string\_A" and
     replace them with the new string "string\_B" 

To check whether your script works or not, make it executable and try it inside the directory
"sandbox":

```bash
./find_and_replace et XXX
```

Did you manage to replace all, and only, words "et" by "XXX" in every file inside "sandbox"?

### Task 2

Now imaging that you want to use this script anywhere at anytime. Do you need to copy the script
each time you need it to the working directory? No... of course not. Let's make a directory in your
home where you can store (and execute) your home-made commands.

```bash
cd
mkdir my_bin
```

Now, let's move your brand new "find\_and\_replace" command to "my\_bin".

```bash
mv Training/bash/exercise-6/sandbox/find_and_replace my_bin/.
```

How can we tell our OS that every script in "my\_bin" needs available for its execution at any time?
Easy!:

```bash
echo $PATH
```

The variable PATH stores all directories where your user finds executables (scripts...
commands...). Let's rewrite the content of this variable to include your "my\_bin" directory.

```bash
export PATH=$HOME/my_bin:${PATH}
```

You can check that your "PATH" variable was modified:

```bash
echo $PATH
```

Now, go back to the "sandbox" directory and run in your terminal:

```
find_and_replace XXX et
```

Voilá... The script was used inside "sandbox" (and "find\_and\_replace" is in other directory).

Finnally, if you open a new terminal... will you be able to use the "find\_and\_replace" command
anywhere? How can we fix it?

