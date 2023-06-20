# ``grep``

La primera, `grep`, filtra de manera
muy sencilla líneas según contengan o no el patrón que estás buscando. Un
ejemplo:

```bash
echo "Paso 0   Energía 10.4" > Experimento_626.oup
echo "Paso 0   Temperatura 303" >> Experimento_626.oup
echo "Paso 1   Energía 10.2" >> Experimento_626.oup
echo "Paso 1   Temperatura 300" >> Experimento_626.oup
echo "Paso 2   Energía 10.5" >> Experimento_626.oup
echo "Paso 2   Temperatura 306" >> Experimento_626.oup
echo "Paso 3   Energía 10.1" >> Experimento_626.oup
echo "Paso 3   Temperatura 299" >> Experimento_626.oup
echo "Paso 4   Energía 10.8" >> Experimento_626.oup
echo "Paso 4   Temperatura 302" >> Experimento_626.oup
echo "Paso 5   Energía 10.1" >> Experimento_626.oup
echo "Paso 6   Temperatura 304" >> Experimento_626.oup
```

Podemos fácilmente filtrar las líneas que contienen o no la palabra *Temperatura*:

```bash
grep 'Temperatura' Experimento_626.oup > Temperatura_Experimento_626.oup
grep -v 'Temperatura' Experimento_626.oup > Energía_Experimento_626.oup
```

```bash
more Temperatura_Experimento_626.oup
more Energía_Experimento_626.oup
```

En la terminal de Linux la salida de un comando se puede redireccionar como la
entrada de otro comando. Por ejemplo, podemos filtrar `stdout` como si de un
fichero se tratara:

```bash
less Energía_Experimento_626.oup | grep '10.1' > Energía_10.1_Experimento_626.oup
```

De hecho, es lo que hacemos cuando escribimos la salida de la línea anterior a
un fichero, porque lo podríamos dejar únicamente como:

```bash
less Energía_Experimento_626.oup | grep '10.1'
```

Así por ejemplo podemos concatenar filtros:

```bash
less Experimento_626.oup | grep 'Energía' | grep '10.1'
```

