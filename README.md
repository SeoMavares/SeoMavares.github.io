# seomavares.github.io

Página de portafolio de mis aplicaciones, publicada con GitHub Pages.

Sitio: <https://seomavares.github.io>

## Contenido del repositorio

- `index.html`: la página completa. HTML, CSS y JavaScript en un solo archivo, sin paso de compilación.
- `assets/`: las capturas reales de las aplicaciones, optimizadas para la web (WebP, 720 px de ancho), y los APK que se descargan desde el sitio.
- `PRODUCT.md`: qué es el sitio, para quién es y qué pruebas existen. Contexto para cualquier cambio futuro.
- `.nojekyll`: desactiva el procesado de Jekyll para que los archivos se publiquen tal cual.

## Cómo verla y editarla

Abre `index.html` en cualquier navegador. Los cambios se publican al hacer push a `main`.

## Cómo añadir un proyecto

Copia un bloque `<article class="shell cell-12 reveal">` y cambia el título, el párrafo, las etiquetas y el enlace al repositorio. Las rejillas disponibles son `cell-4`, `cell-5`, `cell-6`, `cell-7`, `cell-8` y `cell-12`, y el ancho total son doce columnas. El `style="--d:0ms"` de cada tarjeta escalona su aparición al cargar.

Las capturas van en `assets/<proyecto>/`, en WebP de 720 px de ancho, y se colocan dentro de un `<div class="shots">`. Caja es el único proyecto con capturas reales; ninguna imagen inventada puede entrar.

Si un proyecto no tiene repositorio público, el pie de la tarjeta lleva solo el botón de descarga (`<a class="btn btn-primary" href="assets/<proyecto>/<apk>" download>`) y ningún enlace a GitHub. El APK se guarda junto a las capturas y no se versiona ninguna versión anterior: se reemplaza el archivo y se actualiza el nombre en el enlace.

## Pendiente

Faltan capturas reales de `lingua-lens-app` y de `miwayomi`. Cuando existan, van al mismo bloque `.shots` dentro de su tarjeta.
