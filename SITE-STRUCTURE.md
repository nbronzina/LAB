# Site Structure — Lab de Mundanidad Forzada

> Última actualización: 26 enero 2026

## Páginas

### 1. Index (`/`)
- **Función:** Poster de una pantalla
- **Contenido:** Logo gigante + frase + 2 CTAs (Manifiesto, La Red)
- **Tiempo de lectura:** Instantáneo

### 2. Manifiesto (`/manifiesto.html`)
- **Función:** Declaración corta y punchy
- **Contenido:**
  - Intro (2 párrafos)
  - Cuatro pilares (nombre + descripción breve)
  - Marcos teóricos (3 autores, una línea cada uno)
  - Principios organizativos (4 items)
  - Cierre + CTA al marco completo
- **Tiempo de lectura:** ~3-5 minutos

### 3. Marco Teórico (`/marco.html`)
- **Función:** Fundamentación académica completa
- **Contenido:**
  - Análisis del contexto
  - Por qué laboratorio
  - Marco conceptual (pilares extendidos)
  - Marcos teóricos decoloniales (Escobar, Rivera Cusicanqui, Santos)
  - Procesos de investigación
  - Impacto y transformación
  - Principios organizativos
  - Fundamentación académica
  - Conclusiones
- **Tiempo de lectura:** ~25-30 minutos

### 4. La Red (`/red.html`)
- **Función:** Practitioners del laboratorio
- **Contenido:**
  - Separación LATAM / Diáspora
  - Cards de practitioners (placeholders)
- **Tiempo de lectura:** ~2 minutos

---

## Navegación

```
index.html
├── manifiesto.html
│   └── marco.html
└── red.html
```

- Index → Manifiesto (tag)
- Index → La Red (tag)
- Manifiesto → Marco (CTA al final)
- Marco → Manifiesto (botón volver)
- Todas → Index (logo clickeable o botón volver)

---

## Componentes Compartidos

### Header Poster (index)

```html
<main class="poster">
  <div class="poster-logo">
    <span>Lab de</span>
    <span>Mundanidad</span>
    <span>Forzada</span>
  </div>
  <p class="poster-frase">...</p>
  <nav class="poster-links">
    <a href="manifiesto.html" class="poster-tag">Manifiesto</a>
    <a href="red.html" class="poster-tag">La red</a>
  </nav>
</main>
```

### Header Compacto (manifiesto, marco, red)

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

### Footer Poster (index)

```html
<footer class="poster-footer">
  <a href="mailto:nicolas.bronzina@gmail.com">nicolas.bronzina@gmail.com</a>
  <span class="poster-est">Est. 2025</span>
</footer>
```

### Noise Overlay (todas las páginas)

```html
<div class="noise-overlay"></div>
```

---

## Meta Tags (todas las páginas)

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
