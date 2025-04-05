# Mapa Interactivo

Aplicación web que muestra un mapa interactivo con ubicaciones de establecimientos y negocios usando datos de un archivo CSV.

## Características

- Visualización de ubicaciones en un mapa interactivo usando Leaflet
- Marcadores de colores generados dinámicamente según la categoría de cada punto
- Filtrado dinámico por categorías
- Información detallada al hacer clic en cada marcador
- Leyenda con explicación de colores por categoría
- Carga de archivos CSV personalizados con cualquier tipo de categorías
- Interfaz simple y directa

## Cómo usar

1. Abre el archivo `map_standalone_v3.html` directamente en tu navegador
2. Selecciona un archivo CSV haciendo clic en el botón de selección
3. Presiona "Cargar datos" para visualizar los puntos en el mapa
4. Usa los filtros que aparecerán en la esquina superior derecha para mostrar/ocultar categorías
5. Haz clic en cualquier marcador para ver más información

### Formato del archivo CSV

Tu archivo CSV debe tener el siguiente formato:
- Separado por punto y coma (;)
- Con encabezados en la primera fila
- Columnas para latitud y longitud (el sistema buscará columnas con nombres que contengan "lat", "lon", "lng")
- Columna para nombre (el sistema buscará columnas con "nom" o "name")
- Columna de categoría (normalmente la última columna)
- Los valores de categoría pueden ser cualquier texto o número - el sistema asignará colores automáticamente

Ejemplos de CSV válidos:
```
Nombre;Latitud;Longitud;Categoría
Mi ubicación;-33,6077;-70,5732;1
Otra ubicación;-33,6073;-70,5721;3
```

O con categorías personalizadas:
```
Nombre;Latitud;Longitud;Tipo
Restaurante El Bueno;-33,4513;-70,6653;Comida
Farmacia Central;-33,4246;-70,6141;Salud
Banco Nacional;-33,4348;-70,6245;Finanzas
```

### Otras opciones para ejecutar la aplicación

Al ser un solo archivo HTML, existen varias formas de ejecutar la aplicación:

**Opción 1: Abrir directamente**
1. Haz doble clic en el archivo `map_standalone_v3.html`
2. Se abrirá automáticamente en tu navegador predeterminado

**Opción 2: Usar un servidor web local**

Si prefieres usar un servidor web local:

#### En Windows (con Python):
1. Abre la línea de comandos (CMD) en la carpeta donde está el archivo HTML:
   ```
   python -m http.server
   ```
2. Abre tu navegador y ve a http://localhost:8000

#### En macOS o Linux:
1. Abre la terminal en la carpeta donde está el archivo HTML:
   ```
   python -m SimpleHTTPServer 8000    # Python 2
   ```
   o
   ```
   python3 -m http.server 8000    # Python 3
   ```
2. Abre tu navegador y ve a http://localhost:8000

**Opción 3: Usar VS Code con Live Server**
1. Si tienes Visual Studio Code:
   - Instala la extensión "Live Server"
   - Abre la carpeta en VS Code
   - Haz clic derecho en map_standalone_v3.html
   - Selecciona "Open with Live Server"

## Requisitos

- Un navegador web moderno con JavaScript habilitado
- Conexión a internet (para cargar Leaflet y OpenStreetMap)
- Al menos un archivo CSV con el formato descrito anteriormente

## Tecnologías utilizadas

- [Leaflet](https://leafletjs.com/) - Biblioteca JavaScript para mapas interactivos
- [PapaParse](https://www.papaparse.com/) - Biblioteca para procesar archivos CSV
- HTML5, CSS3 y JavaScript 