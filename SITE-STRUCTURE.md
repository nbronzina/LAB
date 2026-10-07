# Site Structure — Lab de Mundanidad Forzada

> Última actualización: 7 octubre 2026

## Páginas

Cada página es una carpeta con su `index.html`. Las URLs no llevan `.html`.

| URL | Archivo | Función |
|-----|---------|---------|
| `/` | `index.html` | Poster. Una pantalla: logo, declaración, frase, cuatro links y el último artefacto pegado |
| `/manifiesto/` | `manifiesto/index.html` | Declaración corta. 3 a 5 minutos |
| `/marco/` | `marco/index.html` | Fundamentación académica. 25 a 30 minutos. Se llega desde el manifiesto |
| `/red/` | `red/index.html` | Mapa de la red, fichas (LATAM y diáspora) e invitación a sumarse |
| `/practicas/` | `practicas/index.html` | Cómo funcionan las prácticas, la #01, cómo responder y las respuestas |
| `/practicas/volante/` | `practicas/volante/index.html` | Volante de la práctica para imprimir |
| `/bitacora/` | `bitacora/index.html` | Registro por año. Los artefactos se ven primero |
| cualquier otra | `404.html` | Página no encontrada |

## Navegación

```
/
├── /manifiesto/ → /marco/
├── /red/
├── /practicas/ → /practicas/volante/
└── /bitacora/
```

- La home y `/practicas/` enlazan a un artefacto de la bitácora por su ancla: `/bitacora/#servicio-tecnico`.
- Todos los links internos son absolutos desde la raíz (`/red/`). Los archivos (CSS, fuentes, imágenes) van con ruta relativa.

## Componentes compartidos

| Componente | Dónde | Qué tiene |
|------------|-------|-----------|
| Header compacto | Todas menos la home y la 404 | Logo en una línea (link a `/`) y navegación: Manifiesto, La red, Prácticas, Bitácora. La página actual lleva `aria-current="page"`; una subpágina marca a su sección con `aria-current="true"` |
| Footer | Todas menos la home y la 404 | "Charlemos →", "Est. 2025" y el remiendo |
| Footer del poster | Home y 404 | Lo mismo en una fila. La 404 no lleva remiendo |
| Remiendo | Todas menos la 404 | "Último remiendo:" con la fecha en un `<time>` y el link "Ver historial" al historial de ese archivo en GitHub |
| Ruido de impresión | Todas | `.noise-overlay`. No se imprime |
| Saltar al contenido | Todas menos la 404 | `.skip-link` |

## Componentes por página

**Home** (`body.home-poster`)
- `h1.poster-logo`: el logo en tres líneas. Es el título de la página
- `.poster-declaracion`, `.poster-frase`, `.poster-links` (cuatro `.poster-tag`)
- `.poster-artefacto`: el último artefacto de la bitácora, pegado. Desde 1000 px va abajo a la derecha; más angosto, debajo de los links

**Red** (`body.red-page`)
- `.red-cuerpo`: la grilla de la página. Desde 700 px, la lista a la izquierda y el mapa a la derecha
- `.red-encabezado`: título e introducción
- `nav.red-mapa`: el continente (`img.red-mapa-continente`), los puntos (`ul.red-mapa-puntos`, un `<li>` por ciudad y un `a.punto` por persona) y el sticker `.red-mapa-sumate`. Ver `MAPA.md`
- `.red-grupos`: dos `section.practitioners-grupo`, LATAM y Diáspora (`.practitioners-grupo--diaspora`)
- `article.practitioner-card` con `id`: una ficha. Es el destino de su punto en el mapa
- `.red-cta`: invitación a sumarse

**Prácticas** (`body.bitacora-page`)
- `.practica-como-funciona`, con el link al volante
- `article.practica`: una práctica. Adentro: video con fachada (`.video-facade`), secciones con `h3.practica-subtitulo`, el ejemplo y las respuestas como piezas pegadas (`.artefacto-pieza`), el botón `.practica-cta-boton`

**Volante** (`body.volante-page`)
- `.volante-instrucciones`: título, para qué sirve, botón "Imprimir". No se imprime
- `article.hoja`: la hoja. Es lo único que se imprime y ocupa todo el papel
- `.hoja-pregunta`, `.hoja-consigna`, `.hoja-pie` (QR, dirección, logo), `.hoja-tiras`

**Bitácora** (`body.bitacora-page`)
- `section.bitacora-year`: un año
- `article.bitacora-entry`: una entrada de texto (fecha, título, autor, descripción, link)
- `article.bitacora-entry.bitacora-artefacto` con `id`: un artefacto. La pieza (`a.artefacto-pieza`) y su ficha (`.artefacto-ficha`: fecha, nombre, crédito y `details.artefacto-origen` con "De dónde sale")

## Anclas

| Ancla | Página | Qué es |
|-------|--------|--------|
| `#servicio-tecnico` | `/bitacora/` | Cartel de servicio técnico |
| `#laboratorio-de-innovacion-climatica` | `/bitacora/` | Afiche del Lab IC+ de Chivilcoy |
| `#nombre-apellido` (por ejemplo `#miriam-latorre`) | `/red/` | La ficha de cada persona. En minúsculas, sin tildes y con guiones |

Un ancla publicada no se renombra: puede estar enlazada desde afuera.

## Imágenes

| Carpeta o patrón | Contenido |
|------------------|-----------|
| `img/marca/` | Logo, continente y avatares. No se editan a mano |
| `img/nombre-apellido.webp` | Fotos de las fichas, 80x80 en pantalla |
| `img/artefacto-<nombre>.webp` | Un artefacto a tamaño completo. Es lo que se abre al tocar la pieza |
| `img/artefacto-<nombre>-640.webp`, `-480.webp` | La misma pieza a 640 y 480 px de ancho, para mostrarla en las páginas |
| `img/ejemplo-practica-miriam.webp`, `-640.webp` | El afiche de Miriam. Conserva el nombre con el que se publicó |

Todas las imágenes llevan `width`, `height` y un `alt` que describe lo que se ve.

## Breakpoints

| Ancho | Qué cambia |
|-------|------------|
| hasta 600 px | Poster y header en columna, fichas con la foto arriba |
| desde 700 px | Artefactos de la bitácora con la ficha al lado. En `/red/`, la lista a la izquierda y el mapa fijo a la derecha |
| de 700 a 899 px | En `/red/`, fichas con la foto arriba (la columna es angosta) |
| desde 1000 px | Artefacto de la home abajo a la derecha |

---

*Documento vivo. Se actualiza con cada iteración del proyecto.*
