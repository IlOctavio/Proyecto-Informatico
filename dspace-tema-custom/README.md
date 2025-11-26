# DSpace Tema Custom - UPSO

Este directorio contiene los componentes visuales y configuraciones del tema personalizado de DSpace para la Universidad Provincial del Sudoeste.

## Estructura

### `/estilos`
Contiene los archivos SCSS globales del tema:
- `_global-styles.scss` - Estilos globales personalizados
- `_theme_sass_variable_overrides.scss` - Variables SASS personalizadas
- `_theme_css_variable_overrides.scss` - Variables CSS personalizadas
- `theme.scss` - Archivo principal de estilos

### `/componentes`
Archivos HTML y SCSS de los componentes Angular:
- `header/` - Componente de cabecera
- `footer/` - Componente de pie de página
- `navbar/` - Barra de navegación
- `home-page/` - Página de inicio
- `item-page/` - Páginas de items
- `collection-page/` - Páginas de colecciones
- `community-page/` - Páginas de comunidades
- Y otros componentes personalizados

### `/assets`
Recursos estáticos:
- Imágenes
- Logos
- Iconos
- Fuentes

### `/configuracion`
Archivos de configuración:
- `docker-compose.override.yml` - Configuración de Docker
- `config.yml` - Configuración de DSpace Angular

## Personalización Realizada

1. **Header**: Alineación del botón "Iniciar sesión" con sidebar
2. **Logo**: Centrado vertical corregido
3. **Estilos**: Colores y diseño personalizado para UPSO
4. **Idioma**: Configurado en español por defecto

## Cómo aplicar estos cambios a una nueva instalación

1. Copiar el contenido de `/estilos` a `src/themes/custom/styles/`
2. Copiar el contenido de `/componentes` a `src/themes/custom/app/`
3. Copiar el contenido de `/assets` a `src/themes/custom/assets/`
4. Copiar los archivos de `/configuracion` a sus ubicaciones correspondientes
5. Reiniciar los contenedores Docker

---
Última actualización: 26 de noviembre de 2025
