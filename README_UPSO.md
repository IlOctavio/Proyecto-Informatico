# Repositorio Digital UPSO - Frontend

Este repositorio contiene el código fuente completo del frontend de DSpace Angular para la Universidad Provincial del Sudoeste (UPSO), incluyendo el tema personalizado y la configuración de Docker.

## 🚀 Inicio Rápido

Para levantar el sistema completo (Frontend + Backend + Base de Datos + Solr):

1. **Requisitos previos:**
   - Docker y Docker Compose instalados.
   - Puertos 4000, 8080, 8983 y 5432 libres.

2. **Iniciar servicios:**
   Ejecuta el siguiente comando desde la raíz de este repositorio:

   ```bash
   docker compose -p d9 \
     -f docker/docker-compose.yml \
     -f docker/docker-compose-rest.yml \
     -f docker/docker-compose.override.yml \
     up -d
   ```

3. **Acceso:**
   - **Frontend (Usuario):** http://localhost:4000 (o la IP de tu servidor)
   - **Backend (API):** http://localhost:8080/server

## 📁 Estructura del Proyecto

- **`src/`**: Código fuente de Angular.
- **`src/themes/custom/`**: Tema visual personalizado de la UPSO (logos, colores, estilos).
- **`docker/`**: Archivos de configuración de Docker Compose.
- **`config/`**: Configuración del entorno (URLs, puertos, etc.).

## ⚙️ Configuración

La configuración principal se encuentra en:
- `config/config.yml`: Configuración del frontend (puertos, host, etc.).
- `docker/docker-compose.override.yml`: Variables de entorno para Docker.

## 📝 Notas Importantes

- Este repositorio incluye **todo el frontend** necesario para producción.
- La base de datos y el almacenamiento de archivos (assetstore) se crean en volúmenes de Docker la primera vez que inicias el sistema.
- Si necesitas restaurar la configuración del backend (dspace.cfg, etc.), deberás copiarla manualmente al contenedor `dspace` si no estás usando los valores por defecto.

---
**Universidad Provincial del Sudoeste (UPSO)**
