# Gantt mensual sencillo

Un snippet en R para obtener un diagrama de Gantt mensual basado en tareas y milestones en formato csv, utilizando el genial paquete [Ganttrify](https://github.com/giocomai/ganttrify) desarrollado por [Giorgio Comai](https://github.com/giocomai).

## Output

Podés ver el paso a paso [acá](https://thessaly.github.io/gantt), teniendo en cuenta que no es interactivo, es sólo un html. 

Podés encontrar `Gantt.Rmd` en la carpeta docs, descargarlo y abrirlo en RStudio para ver una versión interactiva.

![](docs/plot.png)

## Formato de ingreso de datos

El input está en dos archivos csv: `tasks.csv` y `spots.csv`.

### Tareas
`tasks.csv` tiene cuatro columnas: 

```
wp,activity,start_date,end_date
1.Analysis,1.1 Finish coding,1,1
2. Missing data,2.1 Detect missing data,2,2
2. Missing data,2.2 Protocols for missing data collection,2,2
```

- `wp` es el bloque que comprende diferentes tareas, su longitud se calcula sumando la duración de las tareas internas, cada wp va numerado
- `activity` debe seguir un esquema numerado 1.1, 1.2, etc., podés numerar muchas actividades con el mismo número si necesitás una actividad intermitente (mirá el ejemplo de la actividad 3.4 en el png)
- `start_date` y `end_date` son números enteros que representan meses a partir de la fecha de inicio del proyecto, que se indica en el código.

### Milestones

`spots.csv` tiene tres columnas: 

```
activity,spot_type,spot_date
3.5 Review State of the Art,D3,10
3.7 Write methods,D4,13
```

- `activity` indica donde se aplicará tu milestone, tiene que ser igual al texto de cualquier actividad que tengas en `tasks.csv`.
- `spot_type` contiene el texto que irá en la etiqueta del milestone
- `spot_date` es un número entero que indica el mes en el que aparecerá la etiqueta.
