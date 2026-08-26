# Gabriel & Eli — Save the Date (sitio para GitHub Pages)

Este paquete contiene el sitio listo para publicar:

- `index.html` — la página completa (autocontenida: no depende de ningún otro archivo del repo salvo los íconos).
- `favicon.png`, `favicon-16.png`, `apple-touch-icon.png` — íconos de pestaña/atajo.
- `og-image.jpg` — la imagen que se muestra cuando el link se comparte en WhatsApp, Instagram, etc.

## 1. Subirlo a GitHub

1. Crea una cuenta en [github.com](https://github.com) si no tienes una.
2. Crea un repositorio nuevo (público). El nombre no importa mucho — por ejemplo `save-the-date`.
3. Sube estos 5 archivos a la raíz del repositorio (botón "Add file → Upload files" en la web de GitHub, o arrastrándolos).
4. Ve a **Settings → Pages** del repositorio.
5. En "Build and deployment", elige **Deploy from a branch**, rama `main`, carpeta `/ (root)`. Guarda.
6. GitHub te va a dar una URL del tipo `https://tu-usuario.github.io/save-the-date/` — en un par de minutos ya está publicado ahí. Pruébalo antes de seguir al dominio propio.

## 2. Conectar el dominio de NIC Chile

Cuando tengas el dominio comprado, hay dos formas de conectarlo. **Recomendamos la opción del subdominio** — es más simple y con mucho menos margen de error.

### Opción A — Subdominio (recomendado): `savethedate.tudominio.cl`

En el panel de DNS de tu dominio en NIC Chile (o del proveedor donde lo administres):

- Agrega un registro **CNAME**:
  - Nombre/Host: `savethedate` (o el subdominio que prefieras, ej. `www`)
  - Valor/Destino: `tu-usuario.github.io`

En GitHub: **Settings → Pages → Custom domain**, escribe `savethedate.tudominio.cl` y guarda. Espera a que aparezca el candado verde "DNS check successful" (puede tardar desde minutos hasta un par de horas).

### Opción B — Dominio pelado: `tudominio.cl`

Requiere apuntar 4 registros **A** al dominio raíz (`@`), a estas IPs de GitHub Pages:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

Si además quieres que `www.tudominio.cl` funcione, agrega también un registro **CNAME** con host `www` apuntando a `tu-usuario.github.io`.

En GitHub: **Settings → Pages → Custom domain**, escribe `tudominio.cl` y guarda.

### Después de conectar el dominio

- Marca la casilla **"Enforce HTTPS"** en Settings → Pages (puede tardar unos minutos en estar disponible después de que el DNS propague) — así el link es `https://` y se ve seguro.
- GitHub crea automáticamente un archivo `CNAME` en el repo con tu dominio — no hace falta que lo subas tú, se genera solo al guardar el dominio en Settings → Pages.

## 3. Antes de publicar: reemplazar el dominio de ejemplo

`index.html` tiene el dominio de ejemplo `tudominio.cl` en dos líneas (las etiquetas `og:image` y `og:url`, que controlan cómo se ve el link al compartirlo por WhatsApp). Una vez que sepas el dominio final, reemplaza `tudominio.cl` por el real en esas dos líneas antes de subir el archivo — así la vista previa en WhatsApp usa la URL correcta.

## 4. Probar la vista previa de WhatsApp

Después de publicar, compártete el link a ti misma por WhatsApp (o pégalo en un chat) para confirmar que aparece la tarjeta con la foto (`og-image.jpg`), el título "Gabriel & Eli — Save the Date" y la fecha. Si no aparece de inmediato, puede ser caché de WhatsApp — probar en un chat distinto o esperar unos minutos suele resolverlo.

## Notas técnicas

- La página es responsiva: se probó en pantallas desde 320px de ancho (iPhone SE) hasta desktop ancho, y en orientación horizontal/pantallas bajas — todo el contenido se reacomoda sin cortarse.
- Al abrir el link aparece al azar una de las 5 direcciones estéticas del proyecto (fotos, tipografía y animación propias de cada una).
- Botón "↻ otra dirección" para ver otra versión sin recargar la página.
- Respeta la preferencia de "reducir movimiento" del sistema operativo del visitante (si la tiene activada, el contenido aparece directamente sin animación).
- Todo el archivo `index.html` es autocontenido (fuentes vía Google Fonts, todo lo demás embebido) — no depende de ningún otro archivo del repo para funcionar, salvo los íconos.
