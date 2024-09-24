![image](https://github.com/user-attachments/assets/dd0f6882-0d3e-4cb5-a7fd-33206fa56daa)# Tutorial: Homogeneizar coordenadas y crear una capa de puntos en QGIS

Este tutorial te guiará a través del proceso de homogeneizar coordenadas y crear una capa de puntos en QGIS a partir de una tabla de coordenadas.

## Instrucciones para instalar QGIS en Windows

1. Ve al sitio web oficial de [QGIS](https://qgis.org/es/site/forusers/download.html) y selecciona la opción para descargar QGIS para Windows.
2. Elige la versión "QGIS Standalone Installer" (generalmente la más reciente).
3. Descarga el archivo `.exe` y ábrelo para comenzar la instalación.
4. Sigue las instrucciones del instalador (acepta los términos y selecciona el directorio de instalación).
5. Una vez finalizada la instalación, abre QGIS desde el menú de inicio.

---

## Paso 1: Preparar tu tabla de coordenadas

### Homogeneización de coordenadas en formato decimal

Si tienes coordenadas con un número de decimales variable como en el siguiente ejemplo:

<img src= "https://github.com/ngmedina/cargarpuntosQGIS/blob/main/images/tutpuntosQGIS1.png" alt="A_1_B06" width="100"/>

Debes homogeneizarlas a un formato consistente para asegurar que QGIS pueda procesarlas correctamente. Aquí te explicamos cómo hacerlo:

### En Excel o LibreOffice Calc

1. **Selecciona la columna** de latitud y longitud.
2. **Aplica el mismo formato a todas las celdas**:
   - En Excel, selecciona la columna completa (por ejemplo, la columna con las coordenadas de latitud), haz clic derecho y selecciona "Formato de celdas".
   - En "Número", selecciona "Número" y ajusta los **decimales** a un número constante (por ejemplo, al mínimo de precisión, 2 decimales).
   - Repite el mismo proceso para la columna de longitud.
   
3. **Ejemplo de coordenadas homogéneas con 5 decimales**:

4. **Exporta la tabla en formato CSV**:
- Guarda tu archivo de Excel o Calc como un archivo CSV. Esto facilita su importación en QGIS.
  En excel `Archivo > Guardar como > CSV UTF-8(delimitado por comas)(.csv)`.

---

## Paso 2: Importar la tabla en QGIS

1. **Abrir QGIS:**
- Inicia QGIS en tu ordenador.

2. **Importar la tabla CSV:**
- En la barra de menú, selecciona `Capa > Añadir capa > Añadir capa de texto delimitado`.

3. **Configurar la importación:**
- Asegúrate de que las casillas "Delimitadores personalizados" y "Punto y come" están marcadas en la parte "Formato de archivo"
- Asegúrate de que la casilla "Es separador decimal es la coma" está marda en la parte "Opciones de registros y campos"
- Selecciona las columnas de X (longitud) y Y (latitud) que contienen las coordenadas.
- Define el sistema de referencia correcto. Si tus coordenadas están en grados decimales, selecciona WGS 84 (EPSG:4326).

<img src= "https://github.com/ngmedina/cargarpuntosQGIS/blob/main/images/tutpuntosQGIS1.png" alt="img2" width="100"/>

4. **Añadir la capa:**
- Haz clic en "Añadir" y luego en "Cerrar". Ahora deberías ver los puntos en el mapa de QGIS, basados en las coordenadas de tu tabla.

5. **Cambiar el estilo de las capas:**
   - Si deseas cambiar el estilo de la capa (colores, bordes, transparencia, etc.), haz clic derecho sobre la capa en el panel de capas y selecciona `Propiedades`.
   - En la pestaña de `Estilo`, puedes ajustar el color de relleno, el grosor de los bordes y otras propiedades visuales de la capa de puntos de Hamatocaulis.

---
## Paso 3: Añadir una capa base con la topografía de la Península Ibérica

Para visualizar mejor los puntos sobre un mapa de referencia, puedes añadir una capa base con la topografía de la Península Ibérica en QGIS. A continuación te explico cómo hacerlo:

1. **Abrir el panel de "Gestor de fuentes de datos"**:
   - En la barra de herramientas, haz clic en el icono de `Administrador de fuentes de datos` que está en el menú `Capas´
     
2. **Añadir una capa base con el XYZ Tiles**:
   - En la ventana del "Administrador de fuentes de datos", selecciona `XYZ` en el menú lateral izquierdo.
   - Haz clic en el botón de `Nuevo` para añadir un servicio de mapa web (WMS/WMTS).
<img src= "https://github.com/ngmedina/cargarpuntosQGIS/blob/main/images/tutpuntosQGIS1.png" alt="img3" width="100"/>

3. **Configurar la capa de topografía**:
   - En la ventana emergente, introduce la siguiente información:
     - **Nombre:** Topografía
     - **URL:** `https://tile.opentopomap.org/{z}/{x}/{y}.png`
   - Haz clic en `OK` para añadir el nuevo servicio.

4. **Añadir la capa base**:
   - Una vez añadido el servicio, en el panel `XYZ Tiles` de la barra lateral, selecciona la nueva capa "Topografía".
   - Haz doble clic en ella para añadirla al mapa.

Ahora deberías ver una capa base con la topografía de la Península Ibérica en el fondo de tu mapa, lo que ayudará a proporcionar un contexto visual mejorado para tus datos de puntos.

<img src= "https://github.com/ngmedina/cargarpuntosQGIS/blob/main/images/tutpuntosQGIS1.png" alt="img3" width="100"/>

---

## Paso 4: Cargar las provincias de España en QGIS

Para añadir una capa que muestre las provincias de España, sigue los siguientes pasos:

1. **Buscar y descargar la capa de provincias de España:**
   - Una buena fuente para obtener datos administrativos, como las provincias de España, es el [Centro Nacional de Información Geográfica (CNIG)](https://centrodedescargas.cnig.es/CentroDescargas/index.jsp).
   - Descarga un archivo comprimido (.zip) de Límites municipales, provinciales y autonómicos. 
   - Arrastra el archivo .zip a la ventana lateral derecha de "Capas"
   - En la ventana emergente selecciona las capas "SHP_ETRS89/II_autonomicas..." y "SHP_ETRS89/II_provinciales..."
 - Haz clic en `Añadir capas`.

<img src= "https://github.com/ngmedina/cargarpuntosQGIS/blob/main/images/tutpuntosQGIS1.png" alt="img4" width="100"/>

2. **Visualizar la capa:**
   - Después de cargar el archivo, deberías ver la capa de provincias en tu mapa de QGIS. Las provincias estarán delimitadas, lo que te permitirá visualizarlas junto a tus datos de puntos.

3. **Cambiar el estilo de las capas:**
   - Si deseas cambiar el estilo de la capa (colores, bordes, transparencia, etc.), haz clic derecho sobre la capa en el panel de capas y selecciona `Propiedades`.
   - En la pestaña de `Estilo`, puedes ajustar el color de relleno, el grosor de los bordes y otras propiedades visuales de la capa de provincias.

Este paso te permitirá añadir los límites administrativos de las provincias de España, lo que puede ser útil para contextualizar tus datos o para realizar análisis geoespaciales dentro de los límites provinciales.

## Paso 5: Verificación y conversión de coordenadas (si es necesario)
2. **Comprobar los puntos:**
- Comprueba que los puntos están donde deben. Pincha sobre cada punto con el icono `i´ de información y verifica que la provincia coincide
  
1. **Reproyectar la capa (si es necesario):**
- Si tus coordenadas no estaban en WGS 84 y ya las importaste, puedes reproyectar la capa.
- Haz clic derecho sobre la capa importada, selecciona `Exportar > Guardar como...`.
- En el menú de "Guardar Capa", selecciona el sistema de referencia deseado (por ejemplo, WGS 84 si es que aún no lo has hecho).

---

## Paso 4: Guardar la capa de puntos

1. **Guardar tu capa de puntos:**
- Haz clic derecho sobre la capa de puntos en la lista de capas y selecciona `Exportar > Guardar como...`.
- Selecciona el formato que deseas. Por ejemplo, puedes guardar la capa como un archivo Shapefile (.shp), que es un formato geoespacial común.

---

## Finalizar

Tras guardar tu capa, ahora puedes utilizarla en tus proyectos de QGIS para visualización, análisis o cualquier otro fin.

---

## Posibles problemas y soluciones

- **Coordenadas en formato incorrecto:**
- Si tus coordenadas están en UTM o en grados/minutos/segundos, primero tendrás que convertirlas antes de importarlas a QGIS. Puedes hacerlo directamente en tu hoja de cálculo o usando herramientas en línea para conversión de coordenadas.

- **Sistema de referencia incorrecto:**
- Si al cargar los puntos en QGIS no aparecen en el lugar correcto, es posible que hayas especificado un sistema de referencia espacial incorrecto. Asegúrate de conocer el sistema utilizado para las coordenadas en tu tabla y selecciona el correcto en QGIS.

- **Tabla con coordenadas dispersas:**
- Si algunas coordenadas están en diferentes formatos o sistemas, será necesario estandarizarlas antes de importar a QGIS.

