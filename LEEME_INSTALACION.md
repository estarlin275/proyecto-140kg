# Proyecto 140 KG — App instalable (PWA)

Panel de entrenamiento personal, adaptable a iPhone y computadora. Mantiene el registro de ejercicios, progreso de press banca, control de piernas, peso corporal, periodización ondulante y exportaciones JSON/CSV/HTML.

## 1. Publicar gratis en GitHub Pages

1. En https://github.com crea un repositorio nuevo, por ejemplo `proyecto-140kg`.
2. Elige la visibilidad del repositorio y crea el repositorio.
3. En la raíz del repositorio, sube **el contenido de esta carpeta**: `index.html`, `manifest.webmanifest`, `service-worker.js`, la carpeta `icons` y el archivo `.nojekyll`.
   - No subas el ZIP sin descomprimir: GitHub Pages necesita los archivos sueltos.
   - No subas tu archivo `Proyecto_140KG_actualizado_....html`, ni copias JSON/CSV con datos personales: GitHub Pages sirve archivos públicamente por URL.
4. En el repositorio entra en **Settings → Pages → Build and deployment → Deploy from a branch**.
5. Elige rama `main` y carpeta `/ (root)`. Pulsa **Save**.
6. Una vez publicado, entra en la URL de Pages mostrada en esa sección. Normalmente seguirá la estructura `https://USUARIO.github.io/proyecto-140kg/` (sustituye USUARIO por tu nombre de GitHub).

## 2. Instalar en iPhone

1. Abre la URL publicada desde **Safari**.
2. Pulsa **Compartir → Añadir a pantalla de inicio**. En versiones recientes, activa **Abrir como app web**.
3. Pulsa **Añadir** y abre el icono **140** de la pantalla de inicio.
4. Abre la app con internet al menos una vez para que se prepare el almacenamiento del modo sin conexión.
5. Activa modo avión y comprueba que puedes abrir la app y registrar una sesión.

## 3. Instalar en computadora

En Chrome/Edge abre la URL publicada y usa la opción **Instalar aplicación** del menú del navegador si aparece. También puedes usarla directamente en el navegador.

## 4. Pasar los entrenamientos del HTML anterior

- Abre el HTML antiguo en el equipo donde se guardaron los registros.
- En **Ajustes**, elige **Exportar copia JSON** y conserva el archivo.
- Abre **la PWA instalada** → Ajustes → **Importar JSON** y selecciona ese respaldo.
- No se sincronizan automáticamente los registros entre navegadores, app instalada y dispositivos. Exporta JSON periódicamente.
- Si importas un JSON, su contenido reemplaza los registros existentes en ese dispositivo: haz antes una copia de seguridad.

## 5. Guardar y actualizar

- Los datos se guardan en el almacenamiento local del navegador/app; ni GitHub ni esta app tienen un servidor que reciba tu información.
- Al borrar los datos del sitio, desinstalar la PWA o usar determinadas limpiezas de almacenamiento, los registros locales pueden perderse. Conserva backups JSON fuera de la app.
- Para actualizar el diseño, cambia los archivos en GitHub. Cambia también la cadena `CACHE_NAME` en `service-worker.js` al editar recursos, para renovar el caché. Los datos locales no se borran normalmente con una simple actualización, siempre que mantengas la URL/origen y la clave de almacenamiento original.

## 6. Notas técnicas

- HTML/CSS/JavaScript local: sin APIs externas ni dependencias de CDN.
- Manifest con `display: standalone` e iconos para iPhone/Android.
- `service-worker.js` almacena el app shell para funcionamiento offline.
- PWA requiere HTTPS o localhost: no basta con abrir `index.html` desde la app Archivos para instalarla.
- Al usar `Guardar HTML actualizado`, la copia HTML lleva sus datos incrustados y puede abrirse aparte como archivo independiente.
