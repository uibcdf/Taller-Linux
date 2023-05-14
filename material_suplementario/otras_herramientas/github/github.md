<br>
<center>
<img src="https://octodex.github.com/images/original.png" width="140">
</center>
<br>

# GitHub

## ¿Qué es GitHub?

GitHub es un repositorio central de proyectos en la nube, principalmente de
software, implementado para el desarrollo en colaboración que opera el
controlador de versiones Git. En esencia, puedes pensar que GitHub es la
evolución social de Git, ya que nace para facilitar el intercambio de
información y colaboración.

En la UIBCDF conocemos que existen otros repositorios en la nube, como GitLab,
pero por motivos historicos y por que muchas de las herramientas
computacionales que usamos son proyectos abiertos en GitHub, es [aquí donde
tenemos nuestros repositorios][github_uibcdf].

GitHub, como cualquier servicio en la nube de centralización de repositorios,
incluyen herramientas útiles para la comunicación entre los colaboradores: [un
panel donde colgar reportes de errores, sugerencias o dudas][issues_board];
[secciones de visualización del progreso del proyecto][pulse] [o de la
contribución de los desarrolladores][contributors], [una sección wiki][wiki],
[un servidor gratuito de webs para documentación][github_pages], etc. 

## ¿Cómo se usa?

Debido a que su comunidad de usuarios es muy grande, existe buena documentación
propia y ajena para entender su uso, por lo que te sugerimos que dediques en este punto unos minutos a revisar las siguientes
páginas:

https://services.github.com/on-demand/es/  (obsoleta... esperando a la nueva versión en español)   
https://guides.github.com/   
https://lab.github.com    

Para usar GitHub, debes seguir algunos sencillos pasos:

### ¿Cómo crear una cuenta en GitHub?

Para crear un usuario en GitHub, sigue los siguientes pasos:

1. Abre el sitio web de GitHub en tu navegador web (https://github.com/ ) y haz
   clic en el botón verde "Sign up" que se encuentra en la esquina superior
   derecha de la página.
2. Ingresa tu dirección de correo electrónico en el campo correspondiente y haz
   clic en el botón "Sign up for GitHub".
3. Ingresa tu nombre de usuario. Este nombre de usuario será la identificación
   de tu perfil de GitHub y se usará para crear la URL de tu perfil.
4. Ingresa una contraseña segura y confirma tu contraseña.
5. Selecciona tu plan de GitHub. GitHub ofrece planes gratuitos y de pago. Si
   eres nuevo en GitHub, es posible que desees comenzar con el plan gratuito y
   luego actualizar a un plan de pago si lo necesitas.
6. Completa el proceso de verificación de tu correo electrónico. GitHub te
   enviará un correo electrónico de confirmación para verificar tu dirección de
correo electrónico. Sigue las instrucciones en el correo electrónico para
completar el proceso de verificación.
7. Una vez que hayas verificado tu dirección de correo electrónico, podrás
   iniciar sesión en tu cuenta de GitHub y comenzar a utilizar la plataforma.

### ¿Cómo crear un nuevo repositorio?

Después de haber iniciado sesión en tu cuenta de GitHub, 

1. Haz clic en el botón verde "New repository" en la página principal. 
2. Dale un nombre a tu repositorio y elige la configuración que desees,
   agregando una pequeña descripción. 
3. Marca la opción "Initialize this repository with a README".
4. Haz clic en el botón "Create repository".

### ¿Cómo hacer un fork de un repositorio en GitHub?

Para hacer un fork de un repositorio en GitHub, debes seguir los siguientes
pasos:

1. Inicia sesión en tu cuenta de GitHub y navega al repositorio del que deseas
   hacer un "Fork".

2. Haz clic en el botón "Fork" que se encuentra en la esquina superior derecha
   de la página.

3. Se abrirá una ventana emergente que te permitirá seleccionar la cuenta en la
   que deseas hacer el fork. Selecciona tu cuenta de GitHub y haz clic en el
botón "Fork".

4. GitHub copiará el repositorio original a tu cuenta de GitHub como un nuevo
   repositorio.

Ahora podrás trabajar en el nuevo repositorio que acabas de crear. Puedes
clonarlo localmente y hacer cambios, agregar nuevos archivos y hacer commits.


### ¿Cómo clonar un repositorio en tu computadora?

Una vez creado el repositorio, puedes clonarlo en tu computadora para trabajar
localmente (es como "descargarlo"). Para ello:

1. Haz clic en el botón verde "Code"  y copia la GitHub CLI del repositorio. 
2. Si no lo has hecho ya, instala gh en tu computadora. En esta página
   encontraras cómo hacerlo.
3. Abre tu terminal y escribe el comando gh repo clone seguido de la GitHub CLI
   que copiaste.
	
> gh repo clone "GitHub CLI"

### ¿Cómo trabajar en tu proyecto?

Una vez que hayas clonado el repositorio en tu computadora, es posible hacer
cambios en los ficheros y carpetas que contiene. Abre el proyecto que desees
modificar en tu editor de código (VIM o eMACS) y comienza a trabajar en él. 

1. Si no lo has hecho ya, instala git en tu computadora. En esta página
   encontraras cómo hacerlo.

2. Cuando hayas hecho cambios que desees subir al repositorio, agrega los
   archivos con:

> git add --all

Crea un commit con:

> git commit -m "Mensaje de commit"

(El "Mensaje de commit" es un breve mensaje que describe los cambios que
realizaste)

Sube los cambios al repositorio remoto en GitHub con:

>  git push.

### ¿Cómo puedes agregar tus cambios al repositorio original?

Si deseas contribuir con tus cambios al repositorio original, puedes enviar una
solicitud de pull request. Sigue estos sencillos pasos:

1. Haz clic en el botón "Pull requests" en la página del repositorio.
2. Haz clic en el botón verde "New pull request". 
3. Selecciona el branch que deseas enviar y el repositorio al que deseas enviar
   la solicitud de pull request.
4. Completa el formulario de solicitud de pull request y haz clic en el botón
   "Create pull request".

 La solicitud de pull request será enviada al propietario original del
repositorio para su revisión y aprobación.

### Comando gh

Recientemente, GitHub ha habilitado una nueva aplicación, el comando gh.

gh es una herramienta de línea de comandos oficial de GitHub que permite a los
usuarios interactuar con la plataforma GitHub desde la terminal. Algunos de los
comandos más comunes que se pueden usar con gh son:

- gh repo clone: clona un repositorio desde GitHub a tu computadora.
- gh repo fork: crea un fork de un repositorio en tu cuenta de GitHub.
- gh issue list: muestra una lista de las issues en un repositorio.
- gh pr create: crea una solicitud de pull request en un repositorio.
- gh pr checkout: descarga y revisa una solicitud de pull request.
- gh release create: crea un lanzamiento en un repositorio.

Estos son solo algunos ejemplos de los muchos comandos que gh ofrece. La
herramienta es muy útil para los desarrolladores que trabajan con GitHub y
prefieren trabajar en la línea de comandos en lugar de la interfaz de usuario
web.

### ¿Cómo instalar el comando gh en tu computadora?

Para instalar el comando gh en tu computadora, sigue estos pasos:

1. Visita la página de descargas de GitHub CLI:
   https://cli.github.com/manual/installation
2. Descarga el instalador apropiado para tu sistema operativo. 
3. Ejecuta el archivo de instalación descargado y sigue las instrucciones en
   pantalla para completar la instalación.
4. Abre una nueva terminal y escribe el comando gh. Si la instalación fue
   exitosa, deberías ver información sobre cómo usar gh y una lista de comandos
disponibles.

Si recibes un error de "comando no encontrado", puede que necesites agregar la
ruta de instalación de gh a tu variable PATH. No te preocupes, sólo sigue
estos pasos:

1. Abre tu terminal.
2. Escribe el comando echo $PATH para mostrar la lista actual de rutas de tu
   variable PATH.
3. Si la ruta de instalación de gh no aparece en la lista, entonces necesitas
   agregarla. Para hacerlo, escribe el siguiente comando en tu terminal,
reemplazando /ruta/de/gh con la ubicación real de la instalación de gh en tu
sistema:

```bash
export PATH="/ruta/de/gh:$PATH"
```

4. Presiona Enter. Este comando agrega la ruta de gh al inicio de tu variable
PATH.
5. Verifica que se ha agregado la ruta correctamente, para ello vuelve a
ejecutar el comando echo $PATH. Ahora deberías ver la ruta de gh al inicio de
la lista.

Si deseas que esta ruta se agregue automáticamente cada vez que abres una nueva
terminal, agrega el comando anterior al archivo de inicio de tu shell (por
ejemplo, ~/.bashrc para Bash o ~/.zshrc para Zsh).

6.  Abre el archivo con tu editor de texto favorito, agrega la línea al final
del archivo y guárdalo.
7. Ya tienes la ruta de instalación de gh agregada a tu variable PATH, así que
ya puedes usar el comando gh desde cualquier lugar en tu sistema.

## Dudas, problemas técnicos y soluciones. <a class="anchor" id="dudas"></a>

Para centralizar esas dudas, sugerencias o soluciones técnicas sobre el tema de este notebook, haz uso del siguiente canal:

[Foro Técnico: GitHub](https://github.com/uibcdf/Academia/issues/3)

## Más recursos útiles <a class="anchor" id="recursos"></a>

El propósito de este notebook es ser un documento únicamente introductorio.
Puedes encontrar -o contribuir añadiendo- más información útil en el siguiente
listado:

### Documentación <a class="anchor" id="documentacion"></a>

El propósito de este notebook es ser un documento únicamente introductorio.
Puedes encontrar -o contribuir añadiendo- más información útil en el siguiente
listado:

https://conociendogithub.readthedocs.io/en/latest/data/dinamica-de-uso/  
https://medium.com/@sthefany/primeros-pasos-con-github-7d5e0769158c  
https://developer.mozilla.org/es/docs/Learn/Using_Github_pages  
https://reviblog.net/2018/03/29/tutorial-de-git-aprende-git-y-github-gitlab-de-manera-facil-rapida-y-sencilla-parte-1/  

https://jahya.net/blog/git-vs-github/  
https://www.youtube.com/githubguides  
https://try.github.io/  
https://www.edureka.co/blog/how-to-use-github/  


https://docs.github.com/es/github    


### Tutoriales, Webinars y cursos gratuitos <a class="anchor" id="tutoriales"></a>


[github_uibcdf]: https://github.com/uibcdf
[issues_board]: https://github.com/uibcdf/Academia/issues
[pulse]: https://github.com/uibcdf/Academia/pulse
[github_pages]: https://pages.github.com/
[wiki]: https://github.com/uibcdf/Academia/wiki
[contributors]: https://github.com/uibcdf/Academia/graphs/contributors

