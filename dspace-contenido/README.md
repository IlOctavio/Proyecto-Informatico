# Contenido de DSpace - UPSO

Este directorio contiene la estructura de comunidades, colecciones e items del repositorio.

## Estructura Exportada

### `estructura-completa.xml`
Archivo XML con la jerarquía completa de comunidades y colecciones:

**Comunidades:**

1. **Repositorio Digital** (123456789/59)
   - Tesis de Doctorado
   - Tesis de Grado
   - Tesis de Maestría
   - Tesis de Seminario Integrador
   - Trabajo Final de Carrera
   - Trabajo Final de Especialización

2. **EdiUPSO** (123456789/63)
   - Cuadernos de cátedra
   - Emprender desde lo público – Ing. José Porras
   - Historias del Sudoeste Bonaerense
   - Libros de resúmenes de las Jornadas de investigación y Extensión del CEDETS
   - Normas APA

## Cómo Importar en una Nueva Instalación

### Importar estructura de comunidades y colecciones:
```bash
docker exec dspace /dspace/bin/dspace structure-builder \
  -f /dspace/import/estructura-completa.xml \
  -e admin@dspace.org
```

### Notas Importantes:
- Los handles (identificadores) se mantendrán si se usa la opción `-k` (keep-handles)
- Se requiere un usuario administrador activo
- Las descripciones y contenido adicional deben configurarse después de la importación

## Metadata Schema
DSpace usa Dublin Core y otros esquemas de metadatos personalizados para los items.

---
Última actualización: 26 de noviembre de 2025
