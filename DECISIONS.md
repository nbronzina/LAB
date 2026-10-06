# Lab de Mundanidad Forzada — Log de Decisiones

> Registro de decisiones de diseño y desarrollo con sus razones.

---

## 2026-01-26 — Sesión Fundacional

### Decisión: Estética inspirada en Mamdani, no copiada

**Contexto:** Buscábamos una dirección visual que no fuera institucional/académica.

**Opciones consideradas:**
1. Copiar estética Mamdani (NYC bodega/taxi)
2. Traducir los principios a contexto LATAM
3. Partir de cero con otra dirección

**Decisión:** Opción 2. Traducir los principios.

**Razón:** La campaña de Mamdani funciona porque "mira hacia los lados, a la ciudad misma" — bodegas, taxis, señalética de Queens. Copiar esos elementos específicos sería importar estética del Norte Global, contradiciendo el propósito del Lab. En cambio, aplicamos el mismo principio a LATAM: colectivos, combis, ferreterías, kioscos, almacenes.

---

### Decisión: Logo = wordmark tipográfico + ícono separado

**Contexto:** Teníamos un logo icónico (mapa LATAM con círculos) y desarrollamos un sistema tipográfico nuevo.

**Opciones consideradas:**
1. Solo wordmark, abandonar el mapa
2. Solo mapa, sin wordmark
3. Conviven: mapa como ícono, wordmark como logo principal
4. Rediseñar el mapa con la nueva estética

**Decisión:** Opción 3/4 combinadas. Conviven, el mapa se puede adaptar si hace falta.

**Razón:** El mapa tiene fuerza conceptual real (anclaje territorial latinoamericano). El wordmark funciona mejor en aplicaciones web. Cada uno tiene su lugar.

---

### Decisión: Sello de goma descartado (por ahora)

**Contexto:** Exploramos la idea del sello burocrático como logo.

**Opciones consideradas:**
1. Oval burocrático
2. Rectangular expediente
3. Circular minimalista
4. Línea de colectivo
5. Fechador

**Decisión:** No implementar. Usar el logo existente.

**Razón:** El sello tiene potencial (ironía de auto-legitimación), pero no era el momento. El mapa + wordmark ya funcionan. El sello queda como idea para futuras aplicaciones (intervenciones, certificados, sellos en documentos).

---

### Decisión: Index simplificado, manifiesto completo aparte

**Contexto:** El index original repetía contenido que ahora está en la página del manifiesto.

**Opciones consideradas:**
1. Mantener todo en una página larga
2. Separar pero mantener resúmenes en index
3. Index como gancho puro, manifiesto como documento completo

**Decisión:** Opción 3.

**Razón:** La home debe generar interés, no satisfacer toda la curiosidad. "¿Por qué laboratorio?" y "Marcos teóricos" son contenido para quien ya está interesado — van en el manifiesto. La home dice: "esto somos, si querés saber más, acá está el manifiesto".

---

### Decisión: Pilares como tags, no como cards con descripción

**Contexto:** Los pilares tenían cards con explicación en el index original.

**Decisión:** Solo los nombres como tags rotados. Sin descripción.

**Razón:** La explicación completa está en el manifiesto. En la home, los nombres funcionan como señales de identidad — "mundanidad forzada", "viveza criolla" son términos que generan curiosidad por sí solos.

---

### Decisión: Red separada en LATAM + Diáspora

**Contexto:** Originalmente las ciudades estaban mezcladas (Buenos Aires, Bogotá, Valencia, Madrid, Vienna).

**Opciones consideradas:**
1. Mezclar todas las ciudades
2. Separar LATAM / Diáspora
3. Usar nacionalidades en vez de ciudades
4. Solo mostrar LATAM, diáspora implícita

**Decisión:** Opción 2, con origen de la diáspora explícito (Brasil → Valencia, no solo Valencia).

**Razón:** Mezclar sugiere equivalencia. No la hay — el Lab es latinoamericano con miembros en diáspora, no "internacional". La flecha muestra el movimiento: son latinoamericanos desplazados, no europeos interesados en LATAM.

---

### Decisión: Página de practitioners separada

**Contexto:** ¿Mostrar nombres y fotos en la home o en página aparte?

**Opciones consideradas:**
1. No mostrar practitioners (colectivo anónimo)
2. Mostrar en la home
3. Página separada accesible desde "La red"

**Decisión:** Opción 3.

**Razón:**
- A favor de mostrar: da legitimidad, la epistemología del Lab valora el conocimiento situado (quién lo produce importa), son 6 personas no 60.
- A favor de página separada: la home queda limpia, evita el look "meet the team" de agencia.
- Solución: existen, pero no en la home.

---

### Decisión: Email personal temporalmente

**Contexto:** El email `hola@mundanidadforzada.org` no existe.

**Decisión:** Usar `nicolas.bronzina@gmail.com` hasta tener dominio propio.

**Razón:** Un email que rebota es peor que un email personal. El dominio se puede comprar después.

---

### Decisión: Drop shadow siempre en azul eléctrico

**Contexto:** ¿De qué color el drop shadow de los títulos?

**Decisión:** Siempre `#1E5EFF` (azul eléctrico), excepto cuando el fondo es azul (entonces negro).

**Razón:** Consistencia. El azul eléctrico es el color de "desplazamiento" en todo el sistema — cajas offset, shadows, bordes de diáspora.

---

### Decisión: Noise overlay global

**Contexto:** ¿Agregar textura de ruido?

**Decisión:** Sí, overlay fijo al 12% de opacidad en todas las páginas.

**Razón:** Simula papel offset barato. Añade calidez sin estorbar la lectura. Es sutil pero presente.

---

### Decisión: Documentación como conocimiento institucional

**Contexto:** Aplicar el marco de "Vibe Coding Camp" — el conocimiento debe acumularse, no perderse en chats.

**Decisión:** Crear `/docs` con:
- `BRAND.md` — Sistema de marca
- `SITE-STRUCTURE.md` — Estructura del sitio
- `DECISIONS.md` — Este archivo
- `IMPRENTA.md` — Brief base para Claude Code

**Razón:** El brief no es instrucción descartable. Cada iteración enriquece el conocimiento base. Los briefs futuros son deltas sobre este conocimiento, no documentos desde cero.

---

### Decisión: El sistema Alambre-Imprenta como personal software

**Contexto:** El flujo de trabajo que estamos usando (Iniciador → Alambre → Imprenta) es un caso de "personal software" según el marco de Fabien Girardin/Próximo Lab.

**Análisis usando arquetipos:**

| Componente | Arquetipo | Función |
|------------|-----------|---------|
| **Iniciador** (Nicolás) | Humano | Visión, validación, conocimiento situado |
| **Alambre** (Claude chat) | Assistant | Articulación conceptual vía lenguaje natural |
| **Imprenta** (Claude Code) | Agent | Materialización, decisiones técnicas, código |
| **Los /docs** | Workflow | Conectan partes, acumulan conocimiento institucional |

**El sistema completo es "in-between software":** Vive en el gap entre "chatear con IA" y "tener artefactos funcionales". Es demasiado específico para que Anthropic lo ofrezca como producto, demasiado necesario para el Lab para dejarlo sin cubrir.

**Decisión:** Reconocer y documentar el sistema como personal software del Lab. No es solo un método de trabajo — es una pieza de infraestructura propia que se refina con el uso.

**Implicaciones:**
- Los docs no son documentación pasiva, son el "código" del workflow
- El conocimiento circula más a través de lenguaje que de repositorios de código
- El sistema se mejora iterativamente como cualquier software
- Podría eventualmente servir como modelo para otros colectivos

---

### Decisión: Index como Poster

**Contexto:** El index anterior tenía demasiadas secciones (declaración, pilares, red, CTA) y se leía como landing de startup.

**Opciones consideradas:**
1. Arreglar la estructura actual (menos padding, mejor jerarquía)
2. Ir a lo radical — poster de una pantalla

**Decisión:** Opción 2. Poster radical.

**Razón:** Máximo impacto, mínima información. El contenido vive en las subpáginas. Una sola pantalla con logo gigante, una frase, dos links.

---

### Decisión: Separar Manifiesto y Marco Teórico

**Contexto:** El "manifiesto" original era un documento académico de ~6000 palabras y ~30 minutos de lectura. Un manifiesto debería ser declarativo, directo y memorable.

**Opciones consideradas:**
1. Acortar el documento existente
2. Dividir en dos: manifiesto corto + marco teórico completo

**Decisión:** Opción 2.

**Nueva estructura:**
- `manifiesto.html` → ~800 palabras, ~3-5 min
- `marco.html` → ~6000 palabras, ~30 min

**Razón:** El manifiesto engancha, el marco profundiza. Cada documento tiene su función. Quien quiere la visión rápida lee el manifiesto; quien quiere entender la fundamentación lee el marco teórico.

---

### Decisión: Footer con CTA

**Contexto:** El footer mostraba el email completo `nicolas.bronzina@gmail.com`.

**Decisión:** Cambiar por CTA "Charlemos →"

**Razón:** Más profesional, colectivo > individual, futuro-proof para cuando haya dominio propio.

---

### Decisión: CTA sumarse a la red

**Contexto:** La página de red mostraba practitioners pero no invitaba a sumarse.

**Decisión:** Agregar "¿Querés sumarte? Escribinos →" al final de red.html

**Razón:** La red debe poder crecer. Invitación explícita.

---

### Decisión: Página Bitácora

**Contexto:** El sitio necesita un lugar para mostrar proyectos y experimentos.

**Decisión:** Crear bitacora.html como registro cronológico de trabajos.

**Razón:** Muestra que el Lab produce, no solo teoriza. Estructura por año permite ver evolución.

---

## 2026-10-07 — Marca: el continente

### Decisión: El continente literal reemplaza al mapa con círculos

**Contexto:** El ícono era un mapa de LATAM en contorno con círculos que escapan. A Nicolás no le gustaba, pero quería conservar la referencia al continente.

**Opciones consideradas:**
1. Alambre: un trazo continuo con un nudo
2. El continente girado 90°, como lectura de "mirar hacia los lados"
3. Sello de trámite
4. El continente literal, relleno y sin girar

**Decisión:** Opción 4.

**Razón:** En palabras de Nicolás: "me gusta porque es literal el continente LATAM". Mantiene el anclaje territorial que ya tenía el mapa (ver decisión de enero) y se reconoce a 16 px. El sello ya estaba descartado desde enero.

---

### Decisión: Proyección Equal Earth

**Contexto:** La primera versión del continente estaba dibujada en Mercator.

**Opciones consideradas:**
1. Mercator
2. Equal Earth (áreas iguales)

**Decisión:** Opción 2, centrada en el meridiano 76° O.

**Razón:** Mercator agranda lo que está lejos del Ecuador. Equal Earth muestra cada territorio con su superficie real. Para un Lab que imagina desde el sur, tiene sentido no heredar la proyección que agranda el norte. El costo: la silueta queda más angosta y un poco menos familiar.

---

### Decisión: Malvinas en la marca

**Decisión:** Sí. Las Islas Malvinas están en todas las versiones y en los tres tamaños.

**Razón:** Decisión de Nicolás. En el favicon de 16 px ocupan un píxel: es el límite físico del tamaño, no una omisión.

---

### Decisión: Sin banda del Ecuador

**Contexto:** Se probó cortar el continente con una banda horizontal en la línea del Ecuador, alineada con el interlineado del wordmark.

**Decisión:** No. El continente va entero.

**Razón:** Nicolás prefirió el continente sin intervenciones.

---

### Decisión: La sombra del continente sigue la del sitio

**Contexto:** Los títulos del sitio usan `text-shadow` en azul eléctrico hacia abajo y a la derecha. En las primeras versiones del logo Alambre la había dibujado hacia la izquierda y con un azul aproximado, sacado de una captura. Se corrigió contra `style.css`.

**Decisión:** El continente y el logo completo llevan el desplazamiento azul `#1E5EFF` abajo a la derecha. Las islas van sin azul.

**Razón:** Es la decisión de enero ("Drop shadow siempre en azul eléctrico") aplicada al ícono. En formas tan chicas como las islas el desplazamiento se vuelve ruido.

---

### Decisión: Tres tamaños ópticos, marca completa por defecto

**Contexto:** A tamaños chicos las Antillas se vuelven puntos sueltos y el istmo desaparece. Alambre armó una versión M (sin Antillas) y una S (engrosada), y entregó los avatares con la M sin avisar. Nicolás pidió "todo full marca".

**Decisión:** La L, con todas las islas, es la opción por defecto y la de los avatares. La M queda para 32 a 64 px si la L se empasta. La S queda para favicons.

**Razón:** La marca es el continente completo. Las versiones reducidas resuelven un problema de píxeles, no cambian la marca.

---

### Decisión: El logo completo es un archivo; en el sitio el wordmark sigue siendo texto

**Contexto:** En enero se decidió que el wordmark tipográfico es el logo principal y el mapa el ícono, y que conviven.

**Decisión:** Se mantiene. Se suma un logo completo (continente + wordmark) como archivo SVG, para donde no hay CSS: redes, `og-image`, documentos. En el sitio no cambia nada del wordmark.

**Razón:** El wordmark de texto es accesible, liviano y ya funciona. Sumar el continente al header o al poster es una decisión de diseño aparte: queda en pendientes.

---

### Decisión: og-image nueva

**Contexto:** La imagen anterior era una captura del wordmark de 1521x475 y 742 KB.

**Decisión:** 1200x630, con el logo completo, la declaración y la frase, en la tipografía real del sitio. Sin el ruido de impresión.

**Razón:** Sin el ruido pesa 65 KB en vez de más de 500, y en una miniatura el grano no se ve.

---

### Decisión: Los artefactos no se explican

**Contexto:** En el post fijado de Instagram, Alambre sumó una placa que decía "Este cartel es de 2031" después de la foto del cartel.

**Decisión:** Fuera. Ninguna pieza del Lab rotula su propia ficción.

**Razón:** Nicolás: "No debe ser self-explanatory". Es la misma definición que da la página de prácticas: un artefacto es algo que alguien vería en ese mundo sin que nadie se lo explique.

---

### Decisión: Mundanidad forzada no es distopía

**Contexto:** El primer borrador del post usaba un ticket de agua racionada y hablaba de "futuros que nadie elige".

**Decisión:** Los ejemplos parten de adaptaciones cotidianas. El artefacto del post es un cartel de servicio técnico: "Se arreglan robots aspiradora, drones, bicis eléctricas. Se liberan asistentes de voz. Repuestos originales y de los otros."

**Razón:** El borrador hacía lo contrario del pilar 4 del manifiesto: generaba extrañamiento en vez de revelar la creatividad que ya existe.

---

### Decisión: Piezas visuales con poco texto

**Contexto:** El primer carrusel tenía placas de 45 a 60 palabras. Nicolás: "Mucho texto, no lo leí."

**Decisión:** Hasta unas 15 palabras por placa. La explicación va en el texto del post.

**Razón:** Legibilidad callejera. Lo que no se lee de pasada no se lee.

---

### Decisión: Prácticas en plural y sin fecha

**Contexto:** La Práctica #01 se lanzó en febrero con cierre en junio y no recibió ninguna entrega.

**Decisión:** Las prácticas no tienen fecha de cierre. La comunicación general habla de "las prácticas", no de la #01.

**Razón:** Una práctica con fecha se lee como convocatoria, y una convocatoria se posterga hasta que vence.

---

### Decisión: La red se nombra abierta

**Decisión:** "Latinoamérica y su diáspora". La diáspora es mundial, no solo España. Al listar países: "Argentina, Brasil, México, Uruguay y contando". Abierta a futuristas y a quien quiera probar por primera vez.

**Razón:** La red no está cerrada y la descripción no tiene que cerrarla.

---

## Decisiones Pendientes

- [x] Dominio propio → `mundanidadforzada.org` está activo (ver `CNAME`)
- [ ] Email con dominio propio
- [x] Contenido real de practitioners (nombres, bios, fotos) → cinco fichas en `/red/`
- [x] Imagen OG para redes sociales → reemplazada el 7 oct 2026
- [x] ¿Agregar año de fundación en algún lugar visible? → Decidido: sí, en footer ("Est. 2025")
- [ ] ¿El continente entra al header (`.logo-small`) o al poster de la home? Hoy es solo ícono
- [ ] Retirar `img/lab-icon.png` (ícono anterior, 1 MB, sin referencias en el sitio) cuando los avatares de redes estén cambiados
- [ ] En la home, "MUNDANIDAD" se corta por la derecha entre 601 y unos 1420 px de ancho de ventana. ¿Sangrado intencional del poster o bug?

---

*Documento vivo. Se actualiza con cada decisión relevante.*
