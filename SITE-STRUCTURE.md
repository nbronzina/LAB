# Site Structure — Lab de Mundanidad Forzada

> Última actualización: 8 octubre 2026

## Páginas

Cada página es una carpeta con su `index.html`. Las URLs no llevan `.html`.

| URL | Archivo | Función |
|-----|---------|---------|
| `/` | `index.html` | Poster. Una pantalla: logo, declaración, frase, cuatro links y el último artefacto pegado |
| `/manifiesto/` | `manifiesto/index.html` | Declaración corta: unas 350 palabras |
| `/marco/` | `marco/index.html` | Fundamentación académica: unas 4.300 palabras. Se llega desde el manifiesto |
| `/red/` | `red/index.html` | Mapa de la red, fichas (LATAM y diáspora) e invitación a sumarse |
| `/practicas/` | `practicas/index.html` | Cómo funcionan las prácticas, la #01, cómo responder y las respuestas |
| `/practicas/volante/` | `practicas/volante/index.html` | Volante de la práctica para imprimir |
| `/bitacora/` | `bitacora/index.html` | Registro por día: anotaciones cortas y, entre ellas, los artefactos |
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
| Header compacto (`header.site-header`) | Todas menos la home y la 404 | El logo chico en tres líneas (`a.logo`, link a `/`) y la navegación (`nav.header-nav`): Manifiesto, La red, Prácticas, Bitácora. La página actual lleva `aria-current="page"`; una subpágina marca a su sección con `aria-current="true"` |
| Footer (`footer.site-footer`) | Todas menos la home y la 404 | "Charlemos →" (`.footer-cta`), las redes del Lab (`.footer-redes`), "Est. 2025" (`.fundacion`) y el remiendo |
| Footer del poster | Home y 404 | Lo mismo en una fila. Entre 601 y 960 px el remiendo baja a un segundo renglón; hasta 600 px va en columna centrada. La 404 no lleva remiendo |
| Remiendo | Todas menos la 404 | "Último remiendo:" con la fecha en un `<time>` y el link "Ver historial" al historial de ese archivo en GitHub |
| Ruido de impresión | Todas | `.noise-overlay`. No se imprime |
| Saltar al contenido | Todas menos la 404 | `.skip-link` |

## Clases compartidas

Piezas de CSS que usa más de una página. Están juntas al principio de `style.css`, en "PIEZAS COMPARTIDAS". Si se cambia una, cambia en todos los lugares donde se usa.

| Pieza | Clases | Dónde |
|-------|--------|-------|
| Recuadro (caja de borde negro) | `.header-nav a`, `.artefacto-origen summary` | Links del header y "De dónde sale" en la bitácora |
| Botón sticker (caja amarilla con sombra) | `.poster-tag`, `.volante-imprimir`, `.red-mapa-sumate` | Links del poster, "Imprimir" del volante, sticker del mapa |
| Pieza pegada (un artefacto) | `.artefacto-pieza`, `.poster-artefacto` | Bitácora, prácticas y home |
| Link de texto (azul, subrayado) | `.entry-description a`, `.entry-link`, `.bitacora-nota a`, `.practitioner-link` y otros | Bitácora, prácticas, volante y red |
| Link de nota (subrayado coral) | `.remiendo a`, `.documento-nota a`, `.pagina-intro a`, `.footer-redes a`, `.poster-footer a` | Remiendo, nota del manifiesto, bajada de una página de lista, redes del footer, footer del poster |
| Página de lista | `body.pagina`, `main.pagina-contenido`, `.pagina-titulo`, `.pagina-intro` | Bitácora, prácticas y volante. `.pagina-titulo` es también el título de la red |
| Cierre con llamado | `.cta-cierre`, `.cta-link`, `.cta-descripcion` | Final del manifiesto y de la bitácora |

Una clase existe solo si `style.css` o un script la usan. No hay clases "por las dudas".

## Componentes por página

**Home** (`body.home-poster`)
- `h1.poster-logo`: el logo en tres líneas. Es el título de la página
- `.poster-declaracion`, `.poster-frase`, `.poster-links` (cuatro `.poster-tag`)
- `.poster-artefacto`: el último artefacto de la bitácora, pegado. Desde 1000 px va abajo a la derecha; más angosto, debajo de los links

**Manifiesto y Marco** (`main.documento`)
- `h1.documento-titulo`, `.documento-nota` y una `section.documento-seccion` por tema. Adentro de `.documento`, los `h2`, `h3`, `p`, `ul` y `blockquote` ya tienen estilo: no llevan clase
- Solo en el manifiesto: `article.pilar-card` (un pilar), `ul.marcos-lista`, `ul.principios-lista`, `.documento-cierre` y el cierre con llamado al marco
- Solo en el marco: `article.pilar-extendido`, `article.marco-extendido` (un autor, en negro), `.subtitulo-seccion` y `.volver-arriba`

**Red**
- `.red-cuerpo`: la grilla de la página. Desde 700 px, la lista a la izquierda y el mapa a la derecha
- `.red-encabezado`: título e introducción
- `nav.red-mapa`: el continente (`img.red-mapa-continente`), los puntos (`ul.red-mapa-puntos`, un `<li>` por ciudad y un `a.punto` por persona) y el sticker `.red-mapa-sumate`. Ver `MAPA.md`
- `.red-grupos`: dos `section.practitioners-grupo`, LATAM y Diáspora (`.practitioners-grupo--diaspora`)
- `article.practitioner-card` con `id`: una ficha. Es el destino de su punto en el mapa
- `.red-cta`: invitación a sumarse

**Prácticas** (`body.pagina`)
- `.practica-como-funciona`, con el link al volante
- `article.practica`: una práctica. Adentro: video con fachada (`.video-facade`), secciones con `h3.practica-subtitulo`, el ejemplo y las respuestas como piezas pegadas (`.artefacto-pieza`), el botón `.practica-cta-boton`

**Volante** (`body.pagina.volante-page`)
- `.volante-instrucciones`: título, para qué sirve, botón "Imprimir". No se imprime
- `article.hoja`: la hoja. Es lo único que se imprime y ocupa todo el papel
- `.hoja-pregunta`, `.hoja-consigna`, `.hoja-pie` (QR, dirección, logo), `.hoja-tiras`

**Bitácora** (`body.pagina`)
- `section.bitacora-year`: un año
- `article.bitacora-dia` con `id` (la fecha: `2026-10-07`, o `2025-11` si solo se sabe el mes): un día
- `h3.bitacora-fecha`: la fecha, que es un link a ese día. Desde 700 px va al margen, a la izquierda de la línea coral, y queda fija mientras se recorre el día
- `ul.bitacora-notas` y adentro, de lo más nuevo a lo más viejo:
  - `li.bitacora-nota`: una anotación
  - `li.bitacora-artefacto` con `id`: un artefacto. La pieza (`a.artefacto-pieza`) y su ficha (`.artefacto-ficha`: nombre en un `h4`, crédito y `details.artefacto-origen` con "De dónde sale")

## Anclas

| Ancla | Página | Qué es |
|-------|--------|--------|
| `#servicio-tecnico` | `/bitacora/` | Cartel de servicio técnico |
| `#laboratorio-de-innovacion-climatica` | `/bitacora/` | Afiche del Lab IC+ de Chivilcoy |
| `#2026-10-07` (la fecha) | `/bitacora/` | Un día de la bitácora. Al llegar por el ancla, la fecha se marca en amarillo |
| `#nombre-apellido` (por ejemplo `#miriam-latorre`) | `/red/` | La ficha de cada persona. En minúsculas, sin tildes y con guiones |

Un ancla publicada no se renombra: puede estar enlazada desde afuera.

## Imágenes

| Carpeta o patrón | Contenido |
|------------------|-----------|
| `img/marca/` | Logo, continente, avatares y banner de LinkedIn. No se editan a mano |
| `img/nombre-apellido.webp` | Fotos de las fichas: 240x240, con fondo transparente. Se ven a 80x80 |
| `img/artefacto-<nombre>.webp` | Un artefacto a tamaño completo. Es lo que se abre al tocar la pieza |
| `img/artefacto-<nombre>-640.webp`, `-480.webp` | La misma pieza a 640 y 480 px de ancho, para mostrarla en las páginas |
| `img/ejemplo-practica-miriam.webp`, `-640.webp` | El afiche de Miriam. Conserva el nombre con el que se publicó |

Todas las imágenes llevan `width`, `height` y un `alt` que describe lo que se ve.

## Breakpoints

| Ancho | Qué cambia |
|-------|------------|
| hasta 600 px | Poster y header en columna, fichas con la foto arriba |
| desde 700 px | En la bitácora, la fecha al margen y los artefactos con la ficha al lado. En `/red/`, la lista a la izquierda y el mapa fijo a la derecha |
| de 700 a 899 px | En `/red/`, fichas con la foto arriba (la columna es angosta) |
| desde 1000 px | Artefacto de la home abajo a la derecha |

---

*Documento vivo. Se actualiza con cada iteración del proyecto.*
