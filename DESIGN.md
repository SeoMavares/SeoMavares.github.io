# Design

<!-- impeccable:design-schema 1 -->

## World

Un solo `index.html`, sin paso de compilación. Negro OLED de fondo con tres brillos radiales muy bajos, tarjetas de doble bisel (bandeja con núcleo concéntrico) y tipografía grande, apretada y clara. El color de acento aparece poco y a propósito: selección de texto, anillo de foco, el tilde de las pruebas y el hover del pie. La página se lee como una superficie oscura y cara, no como una plantilla.

## Palette

Definida una vez en `:root` y usada por nombre en todo el archivo.

| Token | Valor | Uso |
|---|---|---|
| `--bg` | `#050505` | Fondo de la página |
| `--core` / `--core-2` | `#0b0b0c` / `#101012` | Núcleo de las tarjetas, fondo de los bloques mono |
| `--shell-bg` / `--shell-ring` | `rgb(255 255 255 / .04)` / `.09` | Bandeja: relleno y borde |
| `--shell-ring-2` | `rgb(255 255 255 / .16)` | Borde en hover y en estado activo |
| `--text` | `#f5f4f2` | Texto principal |
| `--muted` | `#a3a19c` | Texto secundario (7,6:1 sobre el núcleo) |
| `--accent` | `#f0b03a` | Acento único: selección, foco, tildes, hover del pie |

Sin modo claro: el fondo negro es una instrucción del cliente para esta superficie.

## Type

- **Schibsted Grotesk** (variable, 400-900) para todo lo que se lee.
- **Spline Sans Mono** (variable, 300-700) solo para notación y datos: la fórmula del saldo y la cadena de motores de traducción. No se usa como disfraz de "técnico".
- Ambas desde jsDelivr, precargadas, con `font-display: swap`.
- Display hasta 5.6rem, tracking entre -0.028em y -0.035em (el piso es -0.04em).
- `font-variant-numeric: tabular-nums` en todo el cuerpo, para que las cifras alineen.

## Shape

Radios anidados: bandeja `2rem`, núcleo `calc(2rem - .5rem)`. Pastillas para botones, etiquetas e islas de navegación. Los separadores son filetes de 1px, nunca cajas.

## Motion

Resortes y ease-out exponencial (`cubic-bezier(.23, 1, .32, 1)`). Nada de `linear` ni de un mismo efecto repetido en cada bloque: cada familia de contenido tiene su propio momento.

| Clase | Qué hace | Dónde |
|---|---|---|
| `.lift` | El texto sube desde detrás de su propio recorte | H1 y los H2 de sección |
| `.settle` | Llega desenfocado, se enfoca y se asienta | Tarjetas, párrafos, botones |
| `.expose` | Entra más despacio y con más desenfoque, como si enfocara | Las cuatro capturas |
| `.aside-in` | Entra desde el costado | El panel de la portada |
| `.draw` | El texto sube detrás del filete que se dibuja | Filas de Clientes |

Reglas que no se negocian al tocar esto:

- **El recorte nunca vive en el elemento observado.** `.lift` recorta un `<span>` interno: un elemento con `clip-path` a cero no intersecta y su `IntersectionObserver` no dispara nunca.
- **Sin JavaScript el contenido ya está visible.** El estado oculto cuelga de `html.js`, que agrega el script del `<head>`.
- **Con movimiento reducido no se mueve nada** y el recorte de `.lift` se libera, o el texto quedaría cortado.
- Solo `transform`, `opacity` y `filter`. Nada de propiedades que provoquen recálculo de layout.

## Surfaces

Las partes que no dibujamos también llevan el diseño: `::selection` en acento, `caret-color`, barra de scroll con pulgar propio, `:focus-visible` con anillo de acento desplazado, `text-underline-offset` en los enlaces, y `prefers-reduced-transparency` para apagar el grano y el desenfoque de la isla de navegación.

## Floor checks

Verificado sobre el sitio construido, no sobre la intención:

- **Contraste:** las diez superficies de texto medidas dan entre 7,3:1 y 7,9:1 (mínimo AA 4,5:1).
- **Sin desborde horizontal** a 390, 768, 1024 y 1440. Navegación en una sola línea, 44px de alto.
- **Movimiento reducido:** cero elementos invisibles y cero recortes activos.
- **Teclado:** el primer Tab alcanza el enlace de salto; con el menú móvil abierto el resto de la página sale del orden de tabulación (`inert`).
- **Copy:** sin guiones largos, sin emojis, sin viñetas decorativas, sin "eyebrows" (etiqueta pequeña sobre un titular).
