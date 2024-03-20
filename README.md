<center style='font-size: 20px'> Guía de Capacitación: Mapa Web interactivo con Leaflet-GeoServer (WEB-GIS)</center>

## Introducción
    En esta capacitación, aprenderemos a construir un mapa web interactivo utilizando dos herramientas poderosas: Leaflet y GeoServer. El objetivo es crear un sistema de información geográfica (SIG) basado en la web que permita visualizar y analizar datos geoespaciales de manera efectiva.
## Requisitos previos
### Antes de comenzar, asegúrate de tener lo siguiente:
1. Conocimientos básicos de HTML, CSS y JavaScript.
2. GeoServer instalado y configurado en tu servidor (puede ser local o remoto).
3. Datos geoespaciales (por ejemplo, archivos shapefile, GeoJSON, etc.) que deseas mostrar en el mapa.

## Pasos para crear el mapa web interactivo
### Configuración de GeoServer
1.	Accede a la interfaz web de GeoServer (generalmente en http://localhost:8080/geoserver).
2.	Crea un nuevo almacén de datos (data store) para tus datos geoespaciales.
3.	Pública las capas que deseas mostrar en el mapa.
### Creación del mapa con Leaflet
1.	Crea una estructura básica de HTML con un contenedor para el mapa.
2.	Agrega la librería Leaflet a tu proyecto (puedes usar un CDN o descargarla localmente).
3.	Inicializa el mapa en tu archivo JavaScript:

JavaScript
```js
// Importa Leaflet
import L from 'leaflet';

// Crea un mapa y establece la vista inicial
const map = L.map('map').setView([latitud, longitud], zoom);

// Agrega una capa base (por ejemplo, OpenStreetMap)
L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '© OpenStreetMap contributors'
}).addTo(map);
```

3. Agregar capas desde GeoServer
1.	Utiliza la URL de GeoServer para obtener las capas publicadas (por ejemplo, http://localhost:8080/geoserver/wms).
2.	Agrega las capas al mapa:

JavaScript
```js
// Agrega una capa WMS desde GeoServer
const capaWMS = L.tileLayer.wms('http://localhost:8080/geoserver/wms', {
    layers: 'nombre_de_la_capa',
    format: 'image/png',
    transparent: true
}).addTo(map);
```

### Personalización y funcionalidades adicionales
1.	Personaliza el estilo de las capas (colores, símbolos, etc.).
2.	Agrega marcadores, polígonos o líneas al mapa.
3.	Implementa interacciones como clics en el mapa o información emergente.




#### Javascript
```js
const capaWMS = L.tileLayer.wms('http://localhost:8080/geoserver/wms', {
    layers: 'nombre_de_la_capa',
    format: 'image/png',
    transparent: true
}).addTo(map);
```
