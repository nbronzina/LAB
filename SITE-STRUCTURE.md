# Lab de Mundanidad Forzada — Estructura del Sitio

> Última actualización: 26 enero 2026

---

## Resumen

| Página | URL | Propósito |
|--------|-----|-----------|
| **Index** | `/` | Gancho. Declaración + pilares + red + CTAs |
| **Manifiesto** | `/manifiesto.html` | Documento completo. Lectura larga |
| **Red** | `/red.html` | Practitioners. Quiénes somos |

---

## Index (`index.html`)

### Propósito

Landing page de impacto. Dice "esto somos, acá estamos, si querés saber más → manifiesto". No es un resumen del manifiesto, es un gancho.

### Secciones

```
Header
└── Logo (wordmark con drop shadow)

Declaración
└── Texto corto: "Metodologías de design fiction que emergen de
    realidades latinoamericanas. No aplicamos marcos del Norte
    Global a contextos del Sur — desarrollamos los nuestros."
└── Sticker en "realidades latinoamericanas"

Cuatro Pilares (compacto)
└── Solo tags, sin explicación:
    - Mundanidad forzada
    - Viveza criolla
    - Atar todo con alambre
    - Diseño crítico como revelador

La Red
└── LATAM:
    - Buenos Aires
    - Bogotá
└── Diáspora:
    - Brasil → Valencia
    - México → Valencia
    - México → Vienna
└── Link: "Ver practitioners →" (a red.html)

CTA Manifiesto
└── Botón: "Leer manifiesto completo →"

Footer
└── Contacto: nicolas.bronzina@gmail.com
└── Est. 2025
```

### Notas

- NO incluye "¿Por qué laboratorio?" (está en manifiesto)
- NO incluye "Marcos teóricos" (está en manifiesto)
- Los pilares son tags rotados, no cards con descripción

---

## Manifiesto (`manifiesto.html`)

### Propósito

Documento completo del Lab. Para quien quiere entender en profundidad.

### Secciones

```
Header Compacto
└── Link "← Volver"
└── Logo pequeño

Título
└── "Manifiesto"
└── Nota: "Documento en continuo desarrollo..."

Introducción
└── El vacío en el futurismo latinoamericano

Análisis del Contexto Actual
└── El vacío en el futurismo latinoamericano
└── Limitaciones de los enfoques existentes

Por Qué "Laboratorio" en Lugar de "Escuela"
└── Filosofía del conocimiento distribuido
└── Resonancia cultural del concepto
└── Modelo distribuido vs centralizado

Marco Conceptual: Los Cuatro Pilares
└── Mundanidad forzada (extendido)
└── Viveza criolla (extendido)
└── Atar todo con alambre (extendido)
└── Diseño crítico como revelador (extendido)

Marcos Teóricos Decoloniales
└── Arturo Escobar
└── Silvia Rivera Cusicanqui
└── Boaventura de Sousa Santos

Integración con Design Fiction
└── Diferenciación de enfoques del Norte Global
└── Artefactos diegéticos anti-extractivistas
└── Mundanidad forzada y visibilización

Procesos de Investigación
└── Metodologías distintivas
└── Metodologías anti-extractivistas

Impacto y Transformación Social

Principios Organizativos

Fundamentación Académica

Conclusiones

Síntesis de Marcos Teóricos

Cierre
└── Blockquote: "Mirar hacia los lados, no hacia arriba."
└── Nota sobre documento vivo

Footer
└── Contacto
└── Est. 2025
```

### Notas

- Lectura larga, priorizar legibilidad
- Container más angosto (750px)
- Más aire entre secciones
- Estética más sobria que home (es para leer)

---

## Red (`red.html`)

### Propósito

Página de practitioners. Quiénes conforman el Lab.

### Secciones

```
Header Compacto
└── Link "← Volver"
└── Logo pequeño

Título
└── "La Red"
└── Intro: "Red distribuida de practitioners conectados
    metodológicamente. El ancla es Latinoamérica —
    algunos trabajamos desde la diáspora."

LATAM
└── Practitioner Card (Buenos Aires, Argentina)
    - Foto
    - Nombre
    - Ubicación
    - Bio breve
└── Practitioner Card (Bogotá, Colombia)

Diáspora
└── Practitioner Card (Brasil → Valencia)
└── Practitioner Card (México → Valencia)
└── Practitioner Card (México → Vienna)

Footer
└── Contacto
└── Est. 2025
```

### Practitioners (5 total)

| Grupo | Origen | Ubicación Actual | Nombre | Bio |
|-------|--------|------------------|--------|-----|
| LATAM | Argentina | Buenos Aires | [TBD] | [TBD] |
| LATAM | Colombia | Bogotá | [TBD] | [TBD] |
| Diáspora | Brasil | Valencia | [TBD] | [TBD] |
| Diáspora | México | Valencia | [TBD] | [TBD] |
| Diáspora | México | Vienna | [TBD] | [TBD] |

### Notas

- Fotos: 80x80px, borde negro, object-fit cover
- Si no hay foto, placeholder negro
- La flecha (→) muestra el movimiento, que es el punto

---

## Navegación

```
index.html
├── manifiesto.html (CTA principal)
└── red.html (desde sección "La red")

manifiesto.html
└── index.html (link "← Volver")

red.html
└── index.html (link "← Volver")
```

---

## Componentes Compartidos

### Header Principal (index)

```html
<header class="header">
  <div class="logo">
    <span>Lab de</span>
    <span>Mundanidad</span>
    <span>Forzada</span>
  </div>
</header>
```

### Header Compacto (manifiesto, red)

```html
<header class="manifiesto-header">
  <div class="container">
    <a href="index.html" class="back-link">← Volver</a>
    <div class="logo logo-small">
      <span>Lab de</span>
      <span>Mundanidad</span>
      <span>Forzada</span>
    </div>
  </div>
</header>
```

### Footer

```html
<footer class="contacto">
  <div class="container">
    <p class="contacto-label">Contacto</p>
    <a href="mailto:nicolas.bronzina@gmail.com" class="contacto-email">nicolas.bronzina@gmail.com</a>
    <p class="fundacion">Est. 2025</p>
  </div>
</footer>
```

### Noise Overlay

Presente en todas las páginas:

```html
<div class="noise-overlay"></div>
```

### Meta Tags (todas las páginas)

```html
<!-- Básicos -->
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>[Título] — Lab de Mundanidad Forzada</title>
<meta name="description" content="[Descripción]">

<!-- Favicon -->
<link rel="icon" type="image/png" sizes="32x32" href="favicon-32.png">
<link rel="icon" type="image/png" sizes="16x16" href="favicon-16.png">
<link rel="apple-touch-icon" href="apple-touch-icon.png">

<!-- Preload Fonts -->
<link rel="preload" href="[URL Archivo Black]" as="font" type="font/woff2" crossorigin>
<link rel="preload" href="[URL Space Grotesk]" as="font" type="font/woff2" crossorigin>

<!-- Google Fonts -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Archivo+Black&family=Space+Grotesk:wght@400;500;700&display=swap" rel="stylesheet">

<!-- Open Graph -->
<meta property="og:type" content="website">
<meta property="og:url" content="[URL]">
<meta property="og:title" content="[Título]">
<meta property="og:description" content="[Descripción]">
<meta property="og:image" content="https://nbronzina.github.io/LAB/og-image.png">

<!-- Twitter -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="[Título]">
<meta name="twitter:description" content="[Descripción]">
<meta name="twitter:image" content="https://nbronzina.github.io/LAB/og-image.png">

<!-- Styles -->
<link rel="stylesheet" href="style.css">
```

---

## Requisitos Técnicos

- HTML + CSS puro (mínimo o cero JS)
- Responsive (breakpoint principal: 600px)
- Optimizado para GitHub Pages
- Sin dependencias externas excepto Google Fonts

---

*Documento vivo. Se actualiza con cada iteración del proyecto.*
