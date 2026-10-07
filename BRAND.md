# Lab de Mundanidad Forzada — Sistema de Marca

> Última actualización: 8 octubre 2026

---

## Filosofía Visual

### "Mirar hacia los lados, no hacia arriba"

La identidad del Lab no aspira a la legitimidad académica o institucional. En vez de mirar hacia arriba (hacia lo corporativo, lo pulido, lo "serio"), mira hacia los lados: a la señalética vernácula latinoamericana.

**Referencias visuales:**
- Carteles de líneas de colectivos (Buenos Aires)
- Toldos de almacenes y kioscos
- Señalética de combis (Lima, México DF)
- Rotulación manual de ferreterías
- Afiches de volantes y propaganda callejera
- Etiquetas de productos genéricos
- Boletos de transporte público vintage

**Inspiración directa:** Campaña de Zohran Mamdani para alcalde de NYC (Forge Design + Tyler Evans). La campaña "miró hacia los lados — a la ciudad misma" en vez de usar la estética patriótica/institucional estándar.

---

## Principios de Diseño

| Principio | Descripción |
|-----------|-------------|
| **Imperfección útil** | Registros desalineados, capas visibles, evidencia del proceso |
| **Urgencia práctica** | Como si se diseñó con deadline de ayer y presupuesto de nada |
| **Legibilidad callejera** | Que se lea desde el colectivo en movimiento, en papel offset barato |
| **Sin pedir permiso** | No espera validación institucional. Existe porque tiene que existir |

---

## Paleta de Colores

### Primarios

| Nombre | Hex | Uso |
|--------|-----|-----|
| **Coral Terracota** | `#E85D4A` | Color principal. Títulos, acentos, elementos de atención |
| **Azul Eléctrico** | `#1E5EFF` | Sombras, acentos secundarios, contraste vibrante |
| **Negro Tinta** | `#1A1A1A` | Texto principal, fondos dramáticos, estructura |

### Soporte

| Nombre | Hex | Uso |
|--------|-----|-----|
| **Crema Papel** | `#F5EDE1` | Fondo principal, sensación de papel offset |
| **Crema Sucia** | `#E8DFD0` | Fondos secundarios, capas de profundidad |
| **Coral Oscuro** | `#C94A3A` | Texto coral sobre fondos claros (mejor contraste) |
| **Amarillo Aviso** | `#F2C94C` | Alertas, señalización, highlights, stickers |
| **Azul Link** | `#0047AB` | Links dentro de un texto. El azul eléctrico no alcanza el contraste para texto chico |
| **Gris** | `#4A4A4A` | Texto secundario chico: fechas, créditos, aclaraciones |

### Variables CSS

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

En `style.css` los colores y las dos tipografías se usan siempre por su variable, nunca escritos a mano. La excepción es la hoja del volante, que va en negro y blanco puros (`#000`, `#fff`) porque es lo que sale de la impresora.

### Combinaciones Recomendadas

- **Coral sobre Negro** — Máximo impacto
- **Negro sobre Crema** — Lectura extendida
- **Crema sobre Azul** — Variación energética
- **Crema sobre Coral** — Secciones destacadas

### Contraste

Medido contra WCAG. Vale para cualquier texto que haya que leer, no para los títulos grandes con sombra.

| Combinación | Contraste | Uso |
|-------------|-----------|-----|
| Negro sobre coral | 5:1 | Botones y texto sobre coral |
| Crema sobre negro | 15:1 | Rótulos, footer |
| Coral oscuro sobre crema | 4:1 | Texto coral desde 19 px en Archivo Black |
| Azul link sobre crema | 7.3:1 | Links dentro de un texto |
| Gris sobre crema | 7.6:1 | Texto secundario chico |
| Coral sobre crema | 2.97:1 | Solo títulos grandes con sombra azul |
| Crema sobre coral | 2.97:1 | Solo títulos grandes. Nunca texto chico ni botones |
| Azul de link sobre coral | 2.4:1 | No se usa |

---

## Tipografía

### Display: Archivo Black

- **Uso:** Títulos, headlines, logo
- **Tratamiento:** Siempre en mayúsculas o capitalización agresiva. Con drop shadow en azul eléctrico para máximo impacto
- **Fuente:** archivos locales en `/fonts` (woff2). Sin Google Fonts
- **Peso:** tiene uno solo. El `@font-face` lo declara para todo el rango (`font-weight: 400 900`) para que el navegador no le invente una negrita encima en títulos y `strong`

### Cuerpo: Space Grotesk

- **Uso:** Textos de cuerpo, navegación, información secundaria
- **Pesos:** 400 (regular), 500 (medium), 700 (bold)
- **Fuente:** archivos locales en `/fonts` (woff2). Sin Google Fonts

### Escala Tipográfica

| Tamaño | Nombre | Uso | Fuente |
|--------|--------|-----|--------|
| 96px | Display XL | Hero, portadas | Archivo Black |
| 64px | Display L | Títulos principales | Archivo Black |
| 48px | Display M | Títulos de sección | Archivo Black |
| 32px | Heading L | Subtítulos | Archivo Black |
| 24px | Heading M | Cards, bloques | Archivo Black |
| 18px | Body L | Texto destacado | Space Grotesk |
| 16px | Body M | Texto principal | Space Grotesk |
| 14px | Body S | Captions, metadata | Space Grotesk |

---

## Logo

### Wordmark Principal

```
LAB DE
MUNDANIDAD
FORZADA
```

- Archivo Black
- Color coral `#E85D4A`
- Drop shadow en azul eléctrico `#1E5EFF`, abajo a la derecha: 6 px en el poster (4 px en el teléfono), 2 px en el header
- Line-height: 0.85 en el poster, 0.9 en el header
- Uppercase

### CSS del Logo

En el sitio el logo es texto y tiene dos tamaños: el del poster de la home y el chico del header.

```css
/* Home: gigante, con las líneas escalonadas */
.poster-logo {
  font-family: var(--display);
  font-size: clamp(2.6rem, calc(11.3vw - 5px), 10rem);
  color: var(--coral);
  text-shadow: 6px 6px 0 var(--azul-electrico);
  line-height: 0.85;
  text-transform: uppercase;
}

/* Header de las páginas internas: chico, sin escalonar */
.logo {
  font-family: var(--display);
  font-size: clamp(1.2rem, 4vw, 1.6rem);
  color: var(--coral);
  text-shadow: 2px 2px 0 var(--azul-electrico);
  line-height: 0.9;
  text-transform: uppercase;
}
```

### Versiones

| Versión | Uso |
|---------|-----|
| Multilínea con shadow | Principal, headers |
| Una línea con shadow | Espacios horizontales |
| "LMF" con shadow | Versión abreviada |
| Logo pequeño (2px shadow) | Headers compactos |

### Ícono: el continente

Desde octubre 2026 el ícono del Lab es **el continente latinoamericano, literal y relleno**. Reemplaza al mapa de contorno con círculos, que se retiró del repo ese mismo mes.

Se usa para:
- Favicon
- Avatar de redes sociales
- Donde haga falta elemento cuadrado/icónico

**Qué es**

- **Territorio:** de México a Tierra del Fuego, más Cuba, La Española, Puerto Rico y las Islas Malvinas.
- **Proyección:** Equal Earth (áreas iguales), centrada en el meridiano 76° O. Cada territorio ocupa su superficie real. No se usa Mercator.
- **Trazo:** datos de Natural Earth 1:50m. El delta del Amazonas y los archipiélagos australes van soldados al continente: a escala de logo se leían como manchas.
- **Color:** coral. En la versión riso lleva una veta azul eléctrico abajo a la derecha, el mismo gesto que el `text-shadow` de los títulos. Va en todo el territorio, islas incluidas.
- **La veta es continua.** Es el área que barre la forma al correrse, no una copia corrida. Así queda pegada a la costa también donde la tierra es más angosta que el corrimiento (Baja California, el istmo, las islas), y nunca se ve el fondo entre el coral y el azul.

**Tres tamaños ópticos**

| Tamaño | Archivos | Cuándo |
|--------|----------|--------|
| **L** | `continente-riso.svg`, `continente-coral.svg`, `continente-crema.svg`, `continente-negro.svg` | Por defecto. Con todas las islas |
| **M** | `continente-m-coral.svg`, `continente-m-crema.svg` | Solo entre 32 y 64 px de alto, si la L se empasta. Sin Antillas, con Malvinas |
| **S** | `continente-s-coral.svg`, `continente-s-crema.svg`, `favicon.svg` | Hasta 32 px. Trazo engrosado para que el istmo exista a 16 px |

**La marca completa (L) es la opción por defecto, también en avatares.** M y S existen para cuando el tamaño en pantalla obliga. No se usan para "limpiar" la imagen.

**Lo que no se hace con el continente**

- No se gira ni se espeja
- No lleva banda ni corte en la línea del Ecuador
- No se le quitan las Malvinas
- No vuelve al contorno con círculos

### Logo completo (continente + wordmark)

El continente a la izquierda y el wordmark en tres líneas escalonadas. Usa las mismas métricas que `.poster-logo`: Archivo Black, mayúsculas, interlineado 0.85, sangrías de 0.3em y 0.6em. La sombra mide 0.05em y va abajo a la derecha: en el continente es la veta continua y en el wordmark la copia corrida de siempre, igual que en el sitio. El continente mide 1.3 veces el alto del bloque de texto y va centrado con él.

Es un archivo, no texto vivo. Se usa donde no hay CSS: redes, `og-image`, documentos, firmas. **En el sitio el wordmark sigue siendo texto** (`.poster-logo`, `.logo`). Si el continente entra al header o al poster es una decisión pendiente (ver `DECISIONS.md`).

| Versión | Archivo | Sobre qué fondo |
|---------|---------|-----------------|
| Riso (coral + azul) | `logo-riso.svg` | Crema, blanco o negro |
| Crema | `logo-crema.svg` | Coral |
| Negro, una tinta | `logo-negro.svg` | Crema o blanco |

Por debajo de unos 140 px de ancho el wordmark deja de leerse. Ahí va el continente solo.

---

## Elementos Visuales

### Ruido de Impresión

Overlay global al 12% de opacidad, simula textura de papel offset barato.

```css
.noise-overlay {
  position: fixed;
  inset: 0;
  opacity: 0.12;
  pointer-events: none;
  z-index: 9999;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 400 400' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
}
```

### Cajas con Offset

Borde desalineado simulando registro de impresión mal hecho.

```css
.card::before {
  content: '';
  position: absolute;
  inset: 0;
  background-color: var(--azul-electrico);
  transform: translate(8px, 8px);
  z-index: -1;
}
```

### Sticker / Etiqueta

Fondo amarillo, ligeramente rotado, para highlights.

```css
.sticker {
  background-color: var(--amarillo-aviso);
  color: var(--negro);
  padding: 0.1em 0.4em;
  display: inline-block;
  transform: rotate(1.5deg);
  font-weight: 700;
}
```

### Rotaciones

Elementos ligeramente rotados (-2° a +2°) para romper la rigidez.

### Pieza pegada

Así se muestra un artefacto en el sitio (home, bitácora, prácticas): como una foto pegada sobre el papel.

- Borde negro de 3 px
- Caja offset azul de 8 px, abajo a la derecha
- Rotación de 1.5° a 2°, hacia un lado o hacia el otro
- Sin epígrafe encima ni al lado. El nombre que lleva es el que la propia pieza dice ("Servicio técnico")
- Al pasar el cursor se endereza

```css
/* --giro: hacia qué lado se inclina. Por defecto, a la izquierda */
.artefacto-pieza {
  position: relative;
  display: block;
  transform: rotate(var(--giro, -1.5deg));
}

.artefacto-pieza::before {
  content: '';
  position: absolute;
  inset: 0;
  background-color: var(--azul-electrico);
  transform: translate(8px, 8px);
  z-index: -1;
}

.artefacto-pieza img {
  border: 3px solid var(--negro);
}
```

### Volante

`/practicas/volante/`. Una hoja para imprimir, cortar y pegar en la calle.

- A una tinta: negro sobre el papel que haya. Sin fondos de color, para que salga bien fotocopiado
- La pregunta en Archivo Black, en tres líneas compuestas al ancho de la hoja, como un afiche tipográfico
- La consigna en tres párrafos cortos, sin vocabulario del Lab ("artefacto diegético", "design fiction")
- QR, dirección escrita y logo a una tinta (`logo-negro.svg`)
- Diez tiras para arrancar con la dirección
- Entra en A4 y en carta

### Mapa de la red

`/red/`. El continente de la marca usado como mapa, con un punto por persona.

- El continente es el archivo de la marca (`continente-riso.svg`). No se redibuja
- Punto negro: vive ahí. Punto azul: salió de ahí, y va en su ciudad de origen
- Cada punto lleva un aro crema que lo despega del coral
- Sin nombres, sin líneas, sin leyenda y sin países. El nombre aparece al pasar el cursor o al llegar con el teclado, y el punto se pone amarillo. Sale arriba del punto, o al costado si arriba tapa a otro
- Varias personas en una ciudad se apilan de a tres por fila
- Un sticker amarillo sobre el Pacífico: "¿Y vos, desde dónde?"
- Desde 700 px va a la derecha de la lista y queda fijo mientras se recorren las fichas

Cómo se suma un punto: `MAPA.md`.

---

## Lo que NO Hacer

| ✗ NO | Razón |
|------|-------|
| Tipografías corporativas (Helvetica, Arial, Roboto, Inter) | Son el opuesto de la estética vernácula |
| Gradientes suaves o glassmorphism | No es una app de Silicon Valley |
| Todo centrado | La asimetría es parte del lenguaje |
| Iconos de librerías estándar | Si hace falta un ícono, que sea dibujado o que no exista |
| Diseño "demasiado limpio" | Si se ve muy pulido, algo está mal |
| Disculparse por la estética | El Lab no pide permiso |

---

## Archivos de Marca

| Archivo | Contenido |
|---------|-----------|
| `favicon.svg` | Continente S, coral, fondo transparente |
| `favicon-16.png`, `favicon-32.png` | Lo mismo en PNG, fondo transparente |
| `apple-touch-icon.png` | 180x180. Continente L riso sobre crema |
| `og-image.png` | Preview para redes sociales (1200x630). Logo completo, declaración y frase |
| `img/marca/logo-riso.svg`, `logo-crema.svg`, `logo-negro.svg` | Logo completo (continente + wordmark) |
| `img/marca/continente-*.svg` | Continente L: riso, coral, crema, negro |
| `img/marca/continente-m-*.svg`, `continente-s-*.svg` | Tamaños ópticos M y S: coral y crema |
| `img/marca/avatar-crema.png` | Avatar 1200x1200. Continente riso sobre crema (LinkedIn) |
| `img/marca/avatar-coral.png` | Avatar 1200x1200. Continente crema sobre coral (Instagram) |
| `img/marca/banner-linkedin.png` | Banner 4200x700. El nombre en coral con sombra azul sobre crema (LinkedIn) |

En los SVG el wordmark está convertido a trazos: no dependen de que la fuente esté cargada.

---

## Redes Sociales

Las piezas para redes usan el mismo sistema que el sitio. No tienen tipografías ni colores propios.

Instagram: `@labmundanidadforzada`. LinkedIn: `linkedin.com/company/108845994`. Las dos están enlazadas en el footer de todas las páginas.

| Pieza | Regla |
|-------|-------|
| Avatar LinkedIn | `avatar-crema.png` |
| Banner LinkedIn | `banner-linkedin.png`, 4200x700. El nombre en tres líneas escalonadas, coral con sombra azul sobre crema, como en la home. Sin continente: el avatar queda al lado y juntos arman el logo completo. El texto va entre el 31% y el 67% del ancho, porque LinkedIn pone el avatar abajo a la izquierda y en el teléfono puede recortar los costados |
| Avatar Instagram | `avatar-coral.png`. Instagram lo recorta en círculo y lo muestra muy chico; el coral se distingue en modo claro y en modo oscuro |
| Placas de carrusel | 1080x1350 (4:5), márgenes de 100 px |
| Títulos | Archivo Black, mayúsculas. Coral con sombra azul `6px 6px 0` sobre crema o negro. Negro sobre coral |
| Texto corrido | Space Grotesk 500 o 700 |
| Etiquetas y numeración | Archivo Black 22 a 26 px, mayúsculas, `letter-spacing: 0.1em` |
| Fondos | Crema, negro o coral, planos |

**Poco texto por placa:** hasta unas 15 palabras. La explicación va en el texto del post, que lee quien se engancha.

---

## Voz Editorial

Estas reglas valen para el sitio, las redes y cualquier pieza del Lab.

**Frases fijas**

- Declaración: "Mirar hacia los lados, no hacia arriba."
- Frase: "Metodologías de design fiction desde contextos latinoamericanos."
- Contexto plegado de un artefacto: "De dónde sale"
- Pie de página: "Último remiendo:" y la fecha

**Idioma:** español rioplatense, con voseo.

**Los artefactos no se explican.** Una pieza del Lab nunca rotula su propia ficción: nada de "esto no existe", "es de 2031" ni "artefacto diegético" pegado encima. El artefacto se muestra como si fuera real y la conexión la hace quien mira. Las fechas y el contexto van, si hacen falta, en la bitácora o en el texto que acompaña.

En el sitio eso tiene forma: la pieza se ve primero y el contexto queda plegado bajo "De dónde sale". El texto alternativo de la imagen describe lo que se ve, como si fuera real: "Cartel pintado a mano en la pared de un servicio técnico", no "artefacto diegético".

**Fuera del sitio, se habla para quien no conoce el Lab.** El volante se lee en la calle: dice "un objeto de ese futuro", no "artefacto diegético".

**Mundanidad forzada no es distopía.** Los ejemplos parten de adaptaciones cotidianas, de viveza criolla y de alambre: un cartel de servicio técnico que arregla robots aspiradora y "libera" asistentes de voz. No parten de escasez dramatizada ni de futuros que asustan. Es el pilar 4: revelar la creatividad que ya existe, sin recurrir al extrañamiento.

**Las prácticas se nombran en plural.** Son ejercicios que se repiten, no tienen fecha de cierre y cualquiera puede responder. La comunicación general habla de "las prácticas", no de la #01.

**La red se nombra abierta.** "Latinoamérica y su diáspora". La diáspora es mundial, no solo España. Cuando se listan países: "Argentina, Brasil, México, Uruguay y contando". Está abierta a futuristas y a quien quiera probar por primera vez.

**La bitácora anota, no presenta.** Una a tres frases por anotación, en primera persona del plural o en impersonal: "Abrimos", "Probamos", "Se suma". Dice qué pasó, sin el camino para llegar: ni borradores, ni versiones descartadas, ni pendientes. Sin adjetivos sobre el propio trabajo. El nombre y el lugar van en la frase cuando informan: "se suma Lucía Guedes, desde Montevideo". Un lugar que no se ubica solo lleva país: "Chivilcoy, Argentina".

**Quién escribe.** El copy nuevo lo articula Alambre y lo valida Nicolás. Imprenta no redacta: si falta un texto, lo pide.

---

*Documento vivo. Se actualiza con cada iteración del proyecto.*
