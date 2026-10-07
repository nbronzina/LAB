# IMPRENTA — Brief Delta: El sitio hace lo que dice

> Fecha: 7 octubre 2026
> Base: Ver `IMPRENTA.md`, `BRAND.md`, `DECISIONS.md`, `SITE-STRUCTURE.md`

---

## Contexto

Nicolás pidió actualizar el sitio. La idea es una sola: que el sitio haga lo que el manifiesto dice. Las decisiones y sus razones están en `DECISIONS.md`, sección "2026-10-07 — Sitio: que haga lo que dice".

Esta vez el código vino con el brief. Alambre hizo los cambios sobre el CSS real y, por pedido de Nicolás, los commiteó directo en la rama por defecto (ver "Commits directos" en `SYSTEM.md`). Tu trabajo es revisar lo publicado y, de acá en más, mantenerlo.

Estos commits también ejecutan `BRIEF-2026-10-07.md` (favicon SVG, Open Graph, documentación al día, sitemap). No hay que hacerlo de nuevo.

---

## Lo que ya está en el repo

| Qué | Dónde | Regla |
|-----|-------|-------|
| Artefacto primero en la bitácora | `bitacora/index.html`, `style.css` ("Artefacto primero") | `BRAND.md`, "Pieza pegada" |
| Último artefacto pegado en la home | `index.html`, `style.css` (`.poster-artefacto`) | Receta "Publicar un artefacto" en `IMPRENTA.md` |
| Primera respuesta a la Práctica #01 | `practicas/index.html` | Lo mismo |
| Volante para imprimir | `practicas/volante/index.html`, `style.css` ("VOLANTE" e "IMPRESIÓN") | `BRAND.md`, "Volante" |
| Remiendo al pie | Todas las páginas menos la 404 | Receta "Actualizar el remiendo" en `IMPRENTA.md` |
| "Proponé un cambio" en el manifiesto | `manifiesto/index.html` | |
| Imágenes nuevas | `img/artefacto-servicio-tecnico.webp`, `-640.webp`, `-480.webp`, `img/ejemplo-practica-miriam-640.webp` | `SITE-STRUCTURE.md`, "Imágenes" |

**Arreglos**

| Qué pasaba | Cómo quedó |
|------------|------------|
| En la home, "MUNDANIDAD" se cortaba entre 601 y 1420 px | `.poster-logo` con `font-size: clamp(2.6rem, calc(11.3vw - 5px), 10rem)` |
| La home y la 404 no tenían `h1` | `.poster-logo` es un `h1` |
| Los títulos en Archivo Black salían con negrita sintética | `@font-face` con `font-weight: 400 900` |
| El botón "Enviar respuesta" tenía texto azul sobre coral (2.4:1) | Texto negro (5:1). Al pasar el cursor, fondo amarillo |
| La pregunta de la práctica iba en coral sobre crema (2.97:1) | Coral oscuro, 1.2rem |
| La imagen del ejemplo no tenía `width` ni `height` | Los tiene |
| El video y el botón de prácticas heredaban el subrayado de los links | Ya no |
| El ruido de impresión salía al imprimir cualquier página | `@media print` lo saca |
| El scroll suave no respetaba "reducir movimiento" | `prefers-reduced-motion` |

---

## Tareas

### 1. Revisar en producción

Abrí el sitio publicado y comprobá:

- [ ] Las ocho páginas cargan sin errores en la consola ni pedidos fallidos
- [ ] El favicon es el continente
- [ ] Al compartir un link, la imagen de preview es la nueva (`og-image.png?v=3`)
- [ ] En la home, el cartel lleva a `/bitacora/#servicio-tecnico`
- [ ] "Ver historial", al pie de cada página, abre el historial de ese archivo en GitHub
- [ ] En `/bitacora/`, "De dónde sale" abre y cierra, y al tocar una pieza se abre la imagen completa

### 2. Imprimir el volante en Firefox y Safari

Se probó en Chromium: sale en una sola página en A4 y en carta, y el QR se lee. Falta probarlo en los otros dos. Si la hoja sale cortada o en dos páginas, anotá qué pasa y avisá. No lo rediseñes.

### 3. De acá en más

Las tareas que se repiten tienen receta en `IMPRENTA.md`: publicar un artefacto, sumar una persona a la red, abrir una práctica nueva.

---

## No tocar

- **`/red/`.** Hay una segunda versión del mapa de la red en camino (ver pendientes en `DECISIONS.md`). No agregues un mapa por tu cuenta.
- **El copy.** El del volante y el de "De dónde sale" están validados por Nicolás. Si falta un texto, pedilo.
- **`font-weight: 400 900`** en el `@font-face` de Archivo Black.
- **Las anclas publicadas** (`#servicio-tecnico`, `#laboratorio-de-innovacion-climatica`).
- **Los archivos de `img/marca/`.**

---

## Cómo se probó

En Chromium, con el sitio servido en local:

- Ocho páginas a doce anchos, de 320 a 1920 px: sin desbordes
- Todos los links internos y las anclas resuelven
- Todas las imágenes cargan y tienen `alt`, `width` y `height`
- Un `h1` por página
- axe: sin infracciones (antes, cuatro: dos de contraste en prácticas, y la falta de `h1` en la home y la 404)
- Lighthouse, móvil y escritorio: 99 a 100 en rendimiento y 100 en accesibilidad, buenas prácticas y SEO. Prácticas pasó de 96 a 100 en accesibilidad
- El volante impreso a PDF en A4 y en carta: una página, QR leído

No se probó: Firefox, Safari, ni una impresora real.

---

## Criterios de Done

- [ ] Revisión en producción completa (tarea 1)
- [ ] Volante probado en Firefox y Safari (tarea 2)
- [ ] Sin cambios en el copy, en `/red/` ni en `img/marca/`

---

## Archivos Afectados

**En estos commits:**
- `index.html`, `404.html`, `manifiesto/index.html`, `practicas/index.html`, `bitacora/index.html`
- `practicas/volante/index.html` (nuevo)
- `marco/index.html`, `red/index.html` (el `<head>` y el remiendo)
- `style.css`, `sitemap.xml`
- `img/artefacto-servicio-tecnico.webp`, `-640.webp`, `-480.webp`, `img/ejemplo-practica-miriam-640.webp` (nuevos)
- `BRAND.md`, `DECISIONS.md`, `SITE-STRUCTURE.md`, `STATUS.md`, `IMPRENTA.md`, `SYSTEM.md`

**Pendientes (los decide Nicolás):** ver el final de `DECISIONS.md`.
