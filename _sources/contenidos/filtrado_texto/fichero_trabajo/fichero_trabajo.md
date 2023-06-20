# Un fichero de texto para trabajar

En primer lugar, y antes de ver cualquier herramienta para el filtrado y reconocimiento de texto,
vamos a presentar un fichero de texto con el que trabajar. Supongamos que hemos realizado un
experimento, el experimento 626, y en un fichero de texto llamado 'Experimento\_626.oup' tenemos el
resultado de medir la temperatura del systema cuando a este se le proporciona cierta cantidad de
energía.

```
Paso 0   Energía 10.4
Paso 0   Temperatura 303
Paso 1   Energía 10.2
Paso 1   Temperatura 300
Paso 2   Energía 10.5
Paso 2   Temperatura 306
Paso 3   Energía 10.1
Paso 3   Temperatura 299
Paso 4   Energía 10.8
Paso 4   Temperatura 302
Paso 5   Energía 10.1
Paso 5   Temperatura 304
```

Para disponer del fichero y poder seguir las siguientes secciones puedes hacer una de las
siguientes cosas:

- Puedes copiar el texto anterior en un fichero que llamarás 'Experimento\_626.oup' haciendo uso
  del editor de tu editor de texto favorito.
- Puedes generar el fichero de texto haciendo uso de la terminal (como verás en la subsección
  siguiente).
- Puedes trabajar con el fichero del repositorio del taller.

## Generando el fichero por terminal

Para generar el fichero por terminal podemos hacer uso del comando ``echo``. Sólo tenemos que
desviar la salida del comando al fichero 'Experimento\_626.oup'. Ejecuta las siguientes lineas en
tu terminal:

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

Ya puedes visualizar el contenido del fichero por terminal:

```bash
less Experimento_626.oup 

# Presiona q para salir de less
```

