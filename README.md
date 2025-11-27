# Proyecto Informático - DSpace UPSO

Backup completo del Repositorio Digital de la Universidad Provincial del Sudoeste (RD-UPSO).

## Contenido del Repositorio

### 📁 `dspace-angular-completo/`
**Código fuente completo del Frontend + Docker**
- Contiene todo el proyecto Angular.
- Incluye carpeta `docker/` con `docker-compose.yml`, `docker-compose-rest.yml`, etc.
- Incluye `src/` con todo el código fuente y el tema custom.
- **Uso:** Esta es la carpeta raíz para levantar el proyecto con Docker.

### 📁 `dspace-configuracion-backend/`
**Configuración crítica del backend (DSpace API)**
- Archivos extraídos del contenedor `dspace`.
- `dspace.cfg`, `submission-forms.xml`, `registries/`, etc.
- **Importante:** Al recrear contenedores, copiar estos archivos a `/dspace/config/` en el contenedor backend.

### 📁 `dspace-contenido/`
**Estructura de comunidades y colecciones**
- `estructura-completa.xml` - Jerarquía completa exportada.

### 📁 `dspace-tema-custom/`
**Backup aislado del tema visual**
- Copia específica de `src/themes/custom` para referencia rápida.

## Instrucciones de Restauración "Desde Cero"

### 1. Clonar Repositorio
```bash
git clone https://github.com/IlOctavio/Proyecto-Informatico.git
cd Proyecto-Informatico
```

### 2. Preparar Entorno Docker
Entrar a la carpeta completa:
```bash
cd dspace-angular-completo
```

### 3. Restaurar Configuración Backend
Antes de iniciar, asegúrate de que los volúmenes de base de datos estén limpios o sean nuevos si es una instalación fresca.
Si vas a usar la configuración personalizada, deberás montarla o copiarla al contenedor una vez iniciado.

### 4. Iniciar Servicios
```bash
docker compose -p d9 \
  -f docker/docker-compose.yml \
  -f docker/docker-compose-rest.yml \
  -f docker/docker-compose.override.yml \
  up -d
```

### 5. Aplicar Configuraciones (Post-Inicio)
Una vez que los contenedores estén corriendo (el backend puede tardar):
```bash
# Copiar configs del backend
docker cp ../dspace-configuracion-backend/dspace.cfg dspace:/dspace/config/
docker cp ../dspace-configuracion-backend/submission-forms.xml dspace:/dspace/config/
# ... copiar el resto según necesidad ...
docker restart dspace
```

### 6. Importar Estructura
```bash
docker cp ../dspace-contenido/estructura-completa.xml dspace:/tmp/
docker exec dspace /dspace/bin/dspace structure-builder -f /tmp/estructura-completa.xml -e admin@dspace.org
```

## Notas Técnicas
- **Base de Datos y Assetstore:** Estos datos viven en volúmenes Docker (`pgdata`, `assetstore`) y no se incluyen en este repositorio git por su tamaño y naturaleza binaria.
- **Node Modules:** No incluidos. Si necesitas desarrollar en Angular localmente, ejecuta `npm install` dentro de `dspace-angular-completo`.

---
Última actualización: 27 de noviembre de 2025
