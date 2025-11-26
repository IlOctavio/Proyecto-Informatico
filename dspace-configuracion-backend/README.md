# Configuración del Backend DSpace - UPSO

Este directorio contiene los archivos de configuración críticos del backend de DSpace.

## Archivos Incluidos

### Configuración Principal
- **`dspace.cfg`** - Archivo de configuración principal de DSpace
  - URLs del servidor y UI
  - Configuración de base de datos
  - Configuración de correo
  - Permisos y políticas

### Configuración de Submisión
- **`submission-forms.xml`** - Define los formularios de envío de items
  - Campos personalizados
  - Validaciones
  - Tipos de input
  
- **`item-submission.xml`** - Define los pasos del proceso de envío
  - Workflow de submisión
  - Secciones del formulario
  - Colecciones asociadas

### Registros
- **`registries/`** - Esquemas de metadatos
  - `dublin-core-types.xml` - Dublin Core
  - `dc-types.xml` - Tipos DC extendidos
  - `bitstream-formats.xml` - Formatos de archivos

### Módulos
- **`modules/`** - Configuración de módulos específicos
  - rest.cfg - Configuración REST API
  - oai.cfg - OAI-PMH
  - etc.

### Spring
- **`spring/`** - Configuración de beans Spring
  - API REST
  - Servicios
  - Seguridad

## Variables de Entorno Importantes

Las siguientes variables se configuran en `docker-compose.override.yml`:

```yaml
dspace__P__server__P__url: http://172.30.14.103:8080/server
dspace__P__ui__P__url: http://172.30.14.103:4000
dspace__P__name: 'Repositorio Digital de la Universidad Provincial del Sudoeste (RD-UPSO)'
default__P__language: es
db__P__maxconnections: 50
```

## Cómo Aplicar en Nueva Instalación

1. Copiar archivos a `/dspace/config/` en el contenedor
2. Ajustar URLs y configuraciones específicas del servidor
3. Reiniciar DSpace backend
4. Verificar que los formularios y metadatos se carguen correctamente

## Personalización Realizada

- **Idioma**: Español por defecto
- **Nombre**: Repositorio Digital UPSO
- **Formularios**: Adaptados a tesis y trabajos académicos
- **Pool de conexiones**: Aumentado para múltiples usuarios

---
Última actualización: 26 de noviembre de 2025
