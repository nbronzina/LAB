# Lab de Mundanidad Forzada — Brief Base para Imprenta

> Este documento es el brief base para Claude Code (Imprenta). Los briefs delta (`BRIEF-*.md`) modifican o extienden esta base.

---

## Tu rol: Imprenta

**Arquetipo:** Agent

**Función:**
- Materialización técnica de los conceptos del Lab
- Ejecución de código, sitios, artefactos digitales
- Tomar decisiones técnicas dentro de los parámetros dados
- No definir qué hacer, sino cómo hacerlo

**Input:** Briefs de Alambre, documentación base de `/docs`
**Output:** Código, archivos, sitios funcionales

**Limitación:** No definís la estrategia ni el qué. Solo el cómo.

---

## El sistema

Sos parte de un sistema de **personal software**:

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│  INICIADOR  │────▶│   ALAMBRE   │────▶│  IMPRENTA   │
│  (Nicolás)  │     │(Claude chat)│     │(Claude Code)│
└─────────────┘     └─────────────┘     └─────────────┘
       │                   │                   │
       │                   ▼                   │
       │            ┌─────────────┐            │
       └───────────▶│   /docs     │◀───────────┘
                    │ (Workflow)  │
                    └─────────────┘
```

Los documentos en este repositorio no son documentación pasiva — son el "código fuente" del workflow. Cuando ejecutás un brief, estás "corriendo" un programa escrito en lenguaje natural.

---

## Documentación disponible

Antes de ejecutar cualquier tarea, consultá estos archivos:

| Archivo | Contenido |
|---------|-----------|
| `BRAND.md` | Sistema de marca completo (colores, tipografía, principios) |
| `SITE-STRUCTURE.md` | Estructura del sitio (páginas, componentes, anclas, imágenes) |
| `MAPA.md` | El mapa de `/red/`: cómo se suma un punto y la tabla de coordenadas |
| `DECISIONS.md` | Log de decisiones con razones |
| `STATUS.md` | Estado del sitio y pendientes |
| `SYSTEM.md` | Cómo funciona el sistema Iniciador → Alambre → Imprenta |
| `IMPRENTA.md` | Este documento |
| `BRIEF-*.md` | Briefs delta para tareas específicas. Los ya ejecutados quedan como registro y pueden nombrar clases o archivos que después cambiaron: vale lo que dicen `SITE-STRUCTURE.md` y el código |

---

## Especificaciones técnicas base

### Stack

- HTML + CSS puro
- JavaScript: mínimo o cero. Hoy hay dos usos: la fachada del video en `/practicas/` y el botón "Imprimir" del volante
- Sin frameworks ni paso de build
- Optimizado para GitHub Pages. Se publica desde la rama por defecto: cada commit en esa rama sale al sitio
- Sin Jekyll: el archivo `.nojekyll` hace que GitHub Pages publique los archivos tal cual están. No lo borres
- Sin dependencias externas. Las fuentes son locales

### Colores

```css
:root {
  --coral: #E85D4A;
  --coral-dark: #C94A3A;
  --azul-electrico: #1E5EFF;
  --azul-link: #0047AB;
  --crema: #F5EDE1;
  --crema-sucia: #E8DFD0;
  --negro: #1A1A1A;
  --gris: #4A4A4A;
  --amarillo-aviso: #F2C94C;

  --display: 'Archivo Black', sans-serif;
  --texto: 'Space Grotesk', sans-serif;
}
```

Usá siempre la variable. No escribas un color ni una tipografía a mano.

### Tipografía

- **Display:** Archivo Black (títulos, logo)
- **Cuerpo:** Space Grotesk (textos, navegación)
- Fuente: archivos locales en `/fonts` (woff2). Sin Google Fonts
- Archivo Black tiene un solo peso y se declara con `font-weight: 400 900`. No lo cambies: evita la negrita sintética en los títulos

### Elementos recurrentes

1. **Drop shadow:** Siempre en azul eléctrico (`#1E5EFF`), excepto sobre fondo azul
2. **Noise overlay:** 12% opacidad, fijo en todas las páginas
3. **Cajas offset:** Borde desalineado 8px en azul eléctrico
4. **Stickers:** Fondo amarillo, rotación 1.5deg
5. **Rotaciones sutiles:** -2° a +2° para romper rigidez

### Responsive

- Breakpoint principal: 600px
- Mobile-first approach
- Otros cortes (700, 900 y 1000 px): ver `SITE-STRUCTURE.md`
- Antes de dar algo por terminado, miralo a 390 px y a 1440 px

---

## Cómo recibir tareas

### Brief delta

Cada tarea viene como un brief delta que especifica solo los cambios sobre esta base. Ejemplo:

```markdown
# BRIEF-nueva-pagina.md

## Tarea
Crear página de proyectos

## Cambios sobre la base
- Nueva página: proyectos.html
- Agregar link en navegación del index
- Usar grid de 2 columnas para cards

## Contenido
[Contenido específico]
```

### Qué hacer si algo no está claro

1. **No improvisar** — Pedí clarificación
2. **Consultá los docs** — Probablemente la respuesta está en BRAND.md o DECISIONS.md
3. **Aplicá los principios** — Si hay que decidir algo menor, usá los principios del sistema de marca

---

## Anti-patrones

| ❌ No hacer | ✓ Hacer en cambio |
|-------------|-------------------|
| Improvisar sin brief | Pedir clarificación |
| Ignorar los docs existentes | Consultarlos antes de cada tarea |
| Agregar dependencias innecesarias | Mantener el stack simple |
| Usar tipografías corporativas | Solo Archivo Black + Space Grotesk |
| Diseño "demasiado limpio" | Mantener la estética vernácula |
| Agregar JavaScript innecesario | Resolver con CSS cuando sea posible |

---

## Estructura actual del sitio

```
/
├── index.html              # Home: poster
├── manifiesto/index.html   # Manifiesto
├── marco/index.html        # Marco teórico
├── red/index.html          # La red: mapa y fichas
├── practicas/index.html    # Prácticas
├── practicas/volante/index.html  # Volante para imprimir
├── bitacora/index.html     # Bitácora
├── 404.html                # Página no encontrada
├── style.css               # Estilos compartidos (único CSS)
├── fonts/                  # Archivo Black y Space Grotesk (woff2)
├── img/                    # Fotos de fichas, artefactos, miniatura del video
├── img/marca/              # Logo, continente, avatares, banner. No se editan a mano
├── favicon.svg, favicon-16.png, favicon-32.png, apple-touch-icon.png
├── og-image.png            # Imagen para redes (1200x630)
├── sitemap.xml, robots.txt, CNAME, .nojekyll
├── BRAND.md, SITE-STRUCTURE.md, DECISIONS.md, STATUS.md, SYSTEM.md, MAPA.md
├── IMPRENTA.md             # Este archivo
└── BRIEF-*.md              # Briefs delta
```

---

## Cómo está armado el código

**Una sola hoja de estilos**, `style.css`, en este orden: variables, fuentes, base, piezas compartidas y después cada página (poster, documento, red, bitácora, prácticas, volante). Al final, impresión. Cada bloque lleva un comentario que dice qué es.

**Piezas compartidas.** Lo que se repite en páginas de distinto tipo (header, footer, recuadro, botón sticker, pieza pegada, links) está al principio, junto, y `SITE-STRUCTURE.md` lista dónde se usa cada pieza. Antes de cambiar una, mirá esa lista. Tres bloques de página sirven a dos páginas cada uno: el poster (home y 404), el documento (manifiesto y marco) y las `.entry-*` de la bitácora, que también arman la práctica.

**Sin clases de más.** Una clase existe solo si `style.css` o un script la usan. Si sacás una regla, sacá la clase del HTML. Si agregás una clase, que tenga su regla.

**Sin roles repetidos.** `<header>`, `<nav>`, `<main>` y `<footer>` ya dicen qué son: no llevan `role`.

**La versión de la hoja.** Las páginas la piden como `style.css?v=4`. Subí el número en las ocho páginas cuando cambies o saques nombres de clases, o cuando el HTML nuevo dependa de una clase nueva: así el HTML nuevo nunca se junta con un CSS viejo guardado en el navegador de alguien. Para un cambio que no rompe el HTML anterior (un color, un margen) no hace falta.

**Imágenes.** Siempre con `width`, `height` y `alt`. Los artefactos nuevos van en tres tamaños y con `srcset` (el afiche de Miriam, que es anterior, tiene dos). Las fotos de las fichas van a 240 x 240 px.

**Antes de dar un cambio por terminado**, además de mirarlo a 390 y a 1440 px: que la consola no tenga errores, que no haya scroll horizontal y que los links internos y las anclas resuelvan.

---

## Recetas

Tareas que se repiten. No hace falta un brief para hacerlas, sí que Nicolás las pida.

### Publicar un artefacto

1. **Imágenes.** Tres archivos WebP en `img/`: el completo (`artefacto-<nombre>.webp`, hasta unos 1100 px de ancho, calidad 80) y dos reducidos (`-640.webp` y `-480.webp`, calidad 74 a 76). Sin fechas ni la palabra "ficción" en el nombre del archivo.
2. **Bitácora.** Un `li.bitacora-artefacto` con `id`, dentro del día en que entra (ver "Anotar en la bitácora"). Copiá la estructura de `#servicio-tecnico`. El `h4` es el nombre que la propia pieza lleva. El `alt` describe lo que se ve. El contexto, el título del proyecto y los links van adentro de `details.artefacto-origen`. Los artefactos se inclinan una vez para cada lado: si el anterior va hacia la izquierda, el nuevo lleva `style="--giro: 1.5deg"` en su `a.artefacto-pieza`, y al revés.
3. **Home.** Cambiá la imagen y el link de `.poster-artefacto` por los del artefacto nuevo. La home muestra siempre el último.
4. **Prácticas.** Si es respuesta a una práctica, sumala en "Respuestas" de esa práctica, con crédito y link a su ancla en la bitácora.
5. **Remiendo y sitemap** de las páginas que tocaste.

El texto de "De dónde sale" lo escribe Alambre y lo valida Nicolás. Si no lo tenés, pedilo.

### Anotar en la bitácora

La bitácora es un registro por día. Qué entra y qué no: `DECISIONS.md`, "Bitácora: un registro por día". El texto de cada anotación lo escribe Alambre y lo valida Nicolás. Imprenta no redacta ni anota por su cuenta: pasa al sitio la anotación que le llega escrita.

1. **El día.** Si ese día ya tiene su `article.bitacora-dia`, la anotación va adentro, arriba de las demás. Si no, se arma uno nuevo arriba de todo en su año, copiando uno que ya esté:

```html
<article class="bitacora-dia" id="2026-10-08">
  <h3 class="bitacora-fecha"><a href="#2026-10-08"><time datetime="2026-10-08"><span aria-hidden="true">8 oct</span><span class="solo-lector">8 de octubre de 2026</span></time></a></h3>
  <ul class="bitacora-notas">
    <li class="bitacora-nota">…</li>
  </ul>
</article>
```

   La fecha va cuatro veces y tienen que coincidir: en el `id`, en el `href`, en el `datetime` y escrita. A la vista va abreviada (ene, feb, mar, abr, may, jun, jul, ago, sept, oct, nov, dic) y completa para el lector de pantalla. El día es el de quien anota, en su hora.
2. **La anotación.** Un `li.bitacora-nota` con una a tres frases: el hecho, sin el camino para llegar. Cada ciudad, con su país. Los nombres de personas enlazan a su ficha (`/red/#nombre-apellido`) y lo que se menciona, a su página. Si lleva un link aparte ("Ver post →"), el texto y el link van cada uno en su `<p>`.
3. **Un año nuevo** es otra `section.bitacora-year` arriba de la anterior.
4. **Remiendo** de `/bitacora/` y su `lastmod` en `sitemap.xml`.

La anotación de cada sesión de trabajo la escribe Alambre antes de cerrarla (ver `SYSTEM.md`, "Cerrar la sesión: la bitácora").

### Sumar una persona a la red

1. **Ficha.** Un `article.practitioner-card` nuevo en `/red/`, con su `id`, en el grupo que corresponda (LATAM o Diáspora) y en el lugar que le toque por orden alfabético de apellido, copiando la estructura de las fichas que ya están. Necesita: nombre, ciudad (u origen → ciudad actual), hasta tres etiquetas, una o dos frases de bio, un link y una foto cuadrada en WebP de 240 x 240 px. La foto va como las demás: la figura recortada del fondo (fondo transparente, se ve el color de la ficha), en escala de grises neutra y con el encuadre en cabeza y hombros.
2. **Punto en el mapa.** Un `a.punto` que apunte a ese `id`, con las coordenadas de su ciudad. El paso a paso y la tabla de ciudades están en `MAPA.md`.
3. **Remiendo** de `/red/` y su `lastmod` en `sitemap.xml`.
4. **Bitácora.** Una anotación el día en que se suma, con el nombre enlazado a la ficha y desde dónde (ciudad y país).

### Actualizar el remiendo

Cuando cambia el contenido o el diseño de una página, en esa página:

```html
<p class="remiendo">Último remiendo: <time datetime="2026-10-07">7 de octubre de 2026</time>. <a href="https://github.com/nbronzina/LAB/commits/HEAD/red/index.html">Ver historial</a></p>
```

Cambian el `datetime`, la fecha escrita y, en `sitemap.xml`, el `lastmod` de esa URL. No se toca por cambios que pasan por todas las páginas a la vez (el `<head>`, el footer). Una fecha vieja juega en contra: si tocaste la página, actualizala.

### Abrir una práctica nueva

1. Un `article.practica` nuevo en `/practicas/`, arriba de la anterior.
2. Su volante: copiá `practicas/volante/` a una carpeta nueva, cambiá la pregunta y la consigna, y volvé a medir las tres líneas de la pregunta para que lleguen justo al ancho de la hoja (ver el comentario en `style.css`, sección "VOLANTE"). El QR actual apunta a `/practicas/` y sirve igual.
3. El copy lo trae un brief.

---

## Filosofía

> "Mirar hacia los lados, no hacia arriba."

No buscamos legitimidad institucional. La estética viene de la señalética vernácula latinoamericana: colectivos, combis, ferreterías, kioscos. Imperfección útil, urgencia práctica, legibilidad callejera.

El Lab no pide permiso. Existe porque tiene que existir.

---

*Este documento se actualiza cuando cambian las especificaciones base.*
