# Diario Norte — Demo interactiva

## Requisitos
Node.js 20.19+ o 22.12+ y npm.

## Ejecutar
```bash
npm install
npm run dev
```
Abrir la URL mostrada por Vite (habitualmente http://localhost:5173).

## Build y despliegue
```bash
npm run build
npm run preview
```
Para Cloudflare Pages: framework Vite, build command `npm run build`, output `dist`. Configurar fallback SPA para rutas internas si la plataforma no lo proporciona. Se incluye `public/_redirects`.

## Recorrido
1. Portada pública con banners, secciones, detalle y archivo.
2. Acceso editorial: elegir **Administradora** o **Editor** (sin credenciales, simulación).
3. Editor: crear borrador y enviarlo a revisión.
4. Cerrar sesión e ingresar como Administradora: revisar y publicar.
5. Abrir la URL pública de la noticia, copiar y compartir.
6. Administradora: gestionar secciones, anuncios, usuarios, configuración, auditoría y archivos.

## Persistencia
Se usa `localStorage` bajo la clave `diario_demo_v1`. Para reiniciar datos: DevTools > Application > Local Storage > borrar la clave, o ejecutar `localStorage.removeItem('diario_demo_v1')` y recargar.

## Límites IMPORTANTES
- Es un prototipo frontend: **no hay autenticación real, API, base de datos, autorización del servidor, subida de archivos, pronóstico real, analíticas, ni protección contra manipulación de localStorage**.
- Los nuevos editores aparecen en el módulo de usuarios; el acceso simulado ofrece los dos roles iniciales, no un sistema real de credenciales.
- Las URLs son rutas SPA de la demo. **No tienen metadatos SEO/Open Graph específicos en el HTML servido**, aunque la navegación funcione. El producto final usará Astro SSR en Cloudflare y ASP.NET Core.
- El control de retención es una simulación de limpieza manual, NO un proceso automático. Antes de eliminar en producción, establecer respaldo, baja lógica, SEO 410/301, referencias de publicidad y políticas legales.
- Las fotos son imágenes externas de Unsplash como contenido ilustrativo, no noticias reales ni fotografías del diario de referencia.
- Las publicidades son demostrativas, sin métricas ni rotación avanzada.
- Los cambios de `localStorage` son por navegador/dispositivo, no se sincronizan entre usuarios.
