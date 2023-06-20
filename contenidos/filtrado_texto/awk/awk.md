# ``awk``

El segundo comando que vemos aquí, `awk`, es un poco más sofisticado a la hora
de hacer búsqueda de patrones de texto. Vamos a poner un ejemplo:

```bash
echo "Paso 0   Energía 10.4" > Experimento_626.oup
echo "Paso 0   Temperatura 303  Distancia 8.2" >> Experimento_626.oup
echo "Paso 1   Energía 10.2" >> Experimento_626.oup
echo "Paso 1   Temperatura 300  Distancia 8.1" >> Experimento_626.oup
echo "Paso 2   Energía 10.5" >> Experimento_626.oup
echo "Paso 2   Temperatura 306  Distancia 8.0" >> Experimento_626.oup
echo "Paso 3   Energía 10.1" >> Experimento_626.oup
echo "Paso 3   Temperatura 299  Distancia 7.8" >> Experimento_626.oup
echo "Paso 4   Energía 10.8" >> Experimento_626.oup
echo "Paso 4   Temperatura 302  Distancia 7.6" >> Experimento_626.oup
echo "Paso 5   Energía 10.1" >> Experimento_626.oup
echo "Paso 5   Temperatura 304  Distancia 7.5" >> Experimento_626.oup
```

Filtremos, como primer caso, según el número de campos. Antes de nada usemos
`awk` para sacar por pantalla el número de campos por línea después de las dos
primeras columnas

```bash
awk '{print $1, $2, NF}' Experimento_626.oup
```

Filtremos entonces las líneas que contienen sólo 4 campos:

```bash
awk '{if (NF==4) print $0}' Experimento_626.oup
```

Ahora, como último ejemplo que ilustra para qué puedes emplear `awk`, filtremos
las líneas en las que existe el patrón *Distancia* y su valor es menor o igual
que 8.0, e imprimamos dicho valor precedido únicamente del índice de paso:

```bash
awk '/Distancia/ {if ($6<=8.0) print $2, $6}' Experimento_626.oup
```

