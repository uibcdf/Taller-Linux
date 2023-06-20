# ``sed``

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

