# Lab de Mundanidad Forzada — Sistema de Marca

> Última actualización: 26 enero 2026

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

### Variables CSS

```css
:root {
  --coral: #E85D4A;
  --coral-dark: #C94A3A;
  --azul-electrico: #1E5EFF;
  --crema: #F5EDE1;
  --crema-sucia: #E8DFD0;
  --negro: #1A1A1A;
  --amarillo-aviso: #F2C94C;
}
```

### Combinaciones Recomendadas

- **Coral sobre Negro** — Máximo impacto
- **Negro sobre Crema** — Lectura extendida
- **Crema sobre Azul** — Variación energética
- **Crema sobre Coral** — Secciones destacadas

---

## Tipografía

### Display: Archivo Black

- **Uso:** Títulos, headlines, logo
- **Tratamiento:** Siempre en mayúsculas o capitalización agresiva. Con drop shadow en azul eléctrico para máximo impacto
- **Fuente:** Google Fonts

### Cuerpo: Space Grotesk

- **Uso:** Textos de cuerpo, navegación, información secundaria
- **Pesos:** 400 (regular), 500 (medium), 700 (bold)
- **Fuente:** Google Fonts

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
- Drop shadow: 4px offset en azul eléctrico `#1E5EFF`
- Line-height: 0.9
- Uppercase

### CSS del Logo

```css
.logo {
  font-family: 'Archivo Black', sans-serif;
  font-size: clamp(2.5rem, 8vw, 4rem);
  color: var(--coral);
  text-shadow: 4px 4px 0 var(--azul-electrico);
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

### Ícono

El ícono del Lab es el **mapa de LATAM con círculos que escapan** (archivo SVG existente). Se usa para:
- Favicon
- Avatar de redes sociales
- Donde haga falta elemento cuadrado/icónico

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
| `favicon-16.png` | Ícono 16x16 |
| `favicon-32.png` | Ícono 32x32 |
| `apple-touch-icon.png` | Ícono para iOS |
| `og-image.png` | Preview para redes sociales (1200x630) |
| `logo-icon.svg` | Mapa LATAM con círculos |

---

*Documento vivo. Se actualiza con cada iteración del proyecto.*
