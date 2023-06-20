# ``apropos``

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

