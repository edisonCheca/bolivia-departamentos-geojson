# bolivia-departamentos-geojson

Límites departamentales de Bolivia en formato GeoJSON, limpios y optimizados para desarrollo web.

---

## 📁 Estructura del Proyecto

```
bolivia-departamentos-geojson/
├── bolivia/                      # Polígono completo de Bolivia
│   └── bolivia.geojson          # País completo (admin_level=2)
├── departamentos/               # Límites departamentales individuales
│   ├── chuquisaca.geojson
│   ├── cochabamba.geojson
│   ├── beni.geojson
│   ├── la-paz.geojson
│   ├── oruro.geojson
│   ├── pando.geojson
│   ├── potosi.geojson
│   ├── santa-cruz.geojson
│   └── tarija.geojson
└── README.md
```

---

## 🗺️ Archivos Disponibles

### 1. **Bolivia Completa** (`bolivia/bolivia.geojson`)
- **Descripción:** Polígono exterior del país sin divisiones internas
- **Nivel Administrativo:** `admin_level=2`
- **Propiedades:** Solo `name: "Bolivia"`
- **Optimización:** Simplificación agresiva (5-10%) para carga rápida
- **Tamaño:** < 1MB
- **Uso:** Vistas generales del mapa de Bolivia

### 2. **Departamentos** (`departamentos/*.geojson`)
- **Descripción:** Límites individuales de los 9 departamentos de Bolivia
- **Nivel Administrativo:** `admin_level=4`
- **Propiedades:** Solo `name: "Nombre del Departamento"`
- **Optimización:** Simplificación moderada para balance entre detalle y rendimiento
- **Uso:** Mapas interactivos, dashboards regionales, análisis por departamento

---

## 📊 Fuente de Datos

- **Origen:** [OpenStreetMap](https://www.openstreetmap.org)
- **Herramienta:** [Overpass Turbo](https://overpass-turbo.eu/)
- **Licencia:** [ODbL (Open Database License)](https://opendatacommons.org/licenses/odbl/)

---

## 🛠️ Criterios Técnicos

### Limpieza de Datos
- ✅ Solo propiedades esenciales (`name`)
- ✅ Sin metadatos innecesarios de OSM
- ✅ Sin relaciones o nodos adicionales

### Optimización
- ✅ Simplificación de geometrías con [MapShaper](https://mapshaper.org/)
- ✅ Bolivia completa: simplificación agresiva (5-10%)
- ✅ Departamentos: simplificación moderada (10-15%)
- ✅ Archivos < 500KB por departamento

### Validación
- ✅ Visualización correcta en GitHub
- ✅ Sin agujeros ni superposiciones
- ✅ Coordenadas en WGS84 (EPSG:4326)
- ✅ Geometrías cerradas y válidas

---

## 🚀 Uso

### JavaScript/Web
```javascript
// Cargar Bolivia completa
fetch('bolivia/bolivia.geojson')
  .then(response => response.json())
  .then(data => console.log(data));

// Cargar un departamento
fetch('departamentos/la-paz.geojson')
  .then(response => response.json())
  .then(data => console.log(data));
```

### Python
```python
import json

# Cargar Bolivia completa
with open('bolivia/bolivia.geojson', 'r', encoding='utf-8') as f:
    bolivia = json.load(f)

# Cargar un departamento
with open('departamentos/cochabamba.geojson', 'r', encoding='utf-8') as f:
    cochabamba = json.load(f)
```

---

## 📝 Listado de Departamentos

1. **Chuquisaca** - Capital: Sucre
2. **Cochabamba** - Capital: Cochabamba
3. **Beni** - Capital: Trinidad
4. **La Paz** - Capital: La Paz
5. **Oruro** - Capital: Oruro
6. **Pando** - Capital: Cobija
7. **Potosí** - Capital: Potosí
8. **Santa Cruz** - Capital: Santa Cruz de la Sierra
9. **Tarija** - Capital: Tarija

---

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Si encuentras errores en los límites o tienes sugerencias de optimización, por favor abre un issue.

---

## 📄 Licencia

Los datos geográficos están bajo licencia [ODbL](https://opendatacommons.org/licenses/odbl/) de OpenStreetMap.

---

## 🔗 Enlaces Útiles

- [OpenStreetMap Bolivia](https://www.openstreetmap.org/relation/252645)
- [Overpass Turbo](https://overpass-turbo.eu/)
- [MapShaper - Herramienta de simplificación](https://mapshaper.org/)
- [GeoJSON Specification](https://geojson.org/)
