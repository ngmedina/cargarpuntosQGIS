# Tutorial: Homogeneizar coordenadas y crear una capa de puntos en QGIS

Este tutorial te guiará a través del proceso de homogeneizar coordenadas y crear una capa de puntos en QGIS a partir de una tabla de coordenadas.

## Paso 1: Preparar tu tabla de coordenadas

1. **Abre tu tabla en Excel** o cualquier otro software de hoja de cálculo compatible (como LibreOffice Calc).

2. Asegúrate de que tienes columnas con las coordenadas X (longitud) y Y (latitud).
   - Los nombres de las columnas podrían ser "Latitud" y "Longitud" o similar. Si no, renómbralas para que sea más fácil identificarlas en QGIS.

3. **Formato homogéneo:**
   - Verifica que todas las coordenadas estén en el mismo sistema de referencia espacial (SRS). El más común es WGS 84 (EPSG:4326), que utiliza grados decimales.
   - Si las coordenadas están en otro formato (por ejemplo, UTM o grados/minutos/segundos), conviene convertirlas a un formato homogéneo antes de importarlas a QGIS.

4. **Exporta la tabla en formato CSV:**
   - Guarda tu archivo de Excel o Calc como un archivo CSV. Esto facilita su importación en QGIS.

## Paso 2: Importar la tabla en QGIS

1. **Abrir QGIS:**
   - Inicia QGIS en tu computadora.

2. **Importar la tabla CSV:**
   - En la barra de menú, selecciona `Capa > Añadir capa > Añadir capa de texto delimitado`.

3. **Configurar la importación:**
   - Asegúrate de que la casilla "Definir geometría a partir de coordenadas" esté marcada.
   - Selecciona las columnas de X (longitud) y Y (latitud) que contienen las coordenadas.
   - Define el sistema de referencia correcto. Si tus coordenadas están en grados decimales, selecciona WGS 84 (EPSG:4326).

4. **Añadir la capa:**
   - Haz clic en "Añadir" y luego en "Cerrar". Ahora deberías ver los puntos en el mapa de QGIS, basados en las coordenadas de tu tabla.

## Paso 3: Verificación y conversión de coordenadas (si es necesario)

1. **Reproyectar la capa (si es necesario):**
   - Si tus coordenadas no estaban en WGS 84 y ya las importaste, puedes reproyectar la capa.
   - Haz clic derecho sobre la capa importada, selecciona `Exportar > Guardar como...`.
   - En el menú de "Guardar Capa", selecciona el sistema de referencia deseado (por ejemplo, WGS 84 si es que aún no lo has hecho).

## Paso 4: Guardar la capa de puntos

1. **Guardar tu capa de puntos:**
   - Haz clic derecho sobre la capa de puntos en la lista de capas y selecciona `Exportar > Guardar como...`.
   - Selecciona el formato que deseas. Por ejemplo, puedes guardar la capa como un archivo Shapefile (.shp), que es un formato geoespacial común.

## Finalizar

Tras guardar tu capa, ahora puedes utilizarla en tus proyectos de QGIS para visualización, análisis o cualquier otro fin.

## Posibles problemas y soluciones

- **Coordenadas en formato incorrecto:**
   - Si tus coordenadas están en UTM o en grados/minutos/segundos, primero tendrás que convertirlas antes de importarlas a QGIS. Puedes hacerlo directamente en tu hoja de cálculo o usando herramientas en línea para conversión de coordenadas.

- **Sistema de referencia incorrecto:**
   - Si al cargar los puntos en QGIS no aparecen en el lugar correcto, es posible que hayas especificado un sistema de referencia espacial incorrecto. Asegúrate de conocer el sistema utilizado para las coordenadas en tu tabla y selecciona el correcto en QGIS.

- **Tabla con coordenadas dispersas:**
   - Si algunas coordenadas están en diferentes formatos o sistemas, será necesario estandarizarlas antes de importar a QGIS.
