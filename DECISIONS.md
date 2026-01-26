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

## Decisiones Pendientes

- [ ] Dominio propio (`mundanidadforzada.org` disponible ~12 USD/año)
- [ ] Email con dominio propio
- [ ] Contenido real de practitioners (nombres, bios, fotos)
- [ ] Imagen OG para redes sociales
- [ ] ¿Agregar año de fundación en algún lugar visible? → Decidido: sí, en footer ("Est. 2025")

---

*Documento vivo. Se actualiza con cada decisión relevante.*
