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

Lo de las islas se corrigió el mismo día: ver "La veta azul es continua y va también en las islas".

---

### Decisión: La veta azul es continua y va también en las islas

**Contexto:** En el continente riso el azul era una copia del coral corrida abajo a la derecha, y las islas iban sin azul. Al verlo en grande, Nicolás marcó dos fallas: "falta Cuba y alrededores con su veta azul" y, en la parte baja de México, "está mal superpuesto el coral y el azul, se deja ver el fondo".

**Opciones consideradas:**
1. Achicar el corrimiento
2. Dejar la copia corrida y sumarla en las islas
3. Una veta continua: el área que barre la forma al correrse

**Decisión:** Opción 3, en todo el territorio.

**Razón:** Donde la tierra es más angosta que el corrimiento (Baja California, el istmo centroamericano, las islas) una copia corrida se despega del coral y deja ver el fondo. El barrido queda siempre pegado a la costa. Dejar las islas sin azul había sido una decisión de Alambre, y fue un error. En el wordmark no cambia nada: las letras son más gruesas que el corrimiento.

Se regeneraron `continente-riso.svg`, `logo-riso.svg`, `apple-touch-icon.png`, `og-image.png` (pasa a `?v=4`) y `avatar-crema.png`.

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

### Decisión: El banner de LinkedIn lleva el nombre

**Contexto:** Nicolás pidió un banner para la página de LinkedIn. Alambre entregó primero la declaración ("Mirar hacia los lados, no hacia arriba.") en negro sobre coral, porque LinkedIn ya escribe el nombre debajo del banner y el avatar ya es el continente. Nicolás preguntó por qué no iba el propio nombre.

**Opciones consideradas:**
1. La declaración, en negro sobre coral
2. El nombre: las tres líneas escalonadas, coral con sombra azul sobre crema

**Decisión:** Opción 2. Sin continente, porque el avatar queda al lado y juntos arman el logo completo.

**Razón:** El nombre que escribe LinkedIn va en su tipografía, no en la del Lab, y el negro sobre coral no lleva la sombra azul. La primera versión quedaba sin las dos cosas que hacen reconocible a la marca. El nombre, además, entra con letras más grandes y en el teléfono se lee mejor.

Medidas: 4200 x 700 px, PNG o JPG, hasta 3 MB. Son las que pide LinkedIn según Sprout Social (mayo 2026) y otras guías que citan su ayuda; la página de ayuda no se pudo abrir directo. Algunas guías siguen dando 1128 x 191, la medida anterior.

---

## 2026-10-07 — Sitio: que haga lo que dice

Una sola idea para toda la actualización: que el sitio haga lo que el manifiesto dice.

### Decisión: En la bitácora, el artefacto va primero

**Contexto:** La bitácora era una lista de texto. El afiche de Miriam estaba descripto y no se veía: para verlo había que salir del sitio.

**Decisión:** Las entradas que son artefactos muestran la pieza, el nombre que la propia pieza lleva y el crédito. El contexto queda plegado bajo "De dónde sale". Las demás entradas (estado del Lab, tutorías, talleres) siguen como estaban.

**Razón:** Es "los artefactos no se explican" aplicado al sitio: primero se encuentra la pieza y el contexto lo abre quien quiere. Cumple lo que la bitácora se propuso en enero: mostrar que el Lab produce, no solo teoriza.

---

### Decisión: La home lleva pegado el último artefacto

**Contexto:** La home decía qué hace el Lab y no mostraba nada hecho.

**Opciones consideradas:**
1. Dejar el poster solo con texto
2. Una galería o un carrusel
3. Una sola pieza, la última de la bitácora, pegada sobre el poster

**Decisión:** Opción 3. Sin epígrafe. Es un link a su entrada en la bitácora y se cambia cuando entra un artefacto nuevo.

**Razón:** El poster sigue siendo una pantalla (decisión de enero) y suma la prueba de lo que dice. Una pieza sola se mira. Una galería se pasa de largo.

Confirmada el mismo día. Al verla publicada, Nicolás preguntó qué aportaba: es el único ejemplo concreto de la portada, y en el teléfono hace que el poster ya no entre en una pantalla. La dejó: "no saques el cartel".

---

### Decisión: El cartel de servicio técnico es la primera respuesta a la Práctica #01

**Contexto:** La práctica llevaba meses con "Todavía no hay respuestas publicadas". El cartel ya era público: es la segunda placa del post fijado de Instagram.

**Decisión:** Entra a la bitácora (octubre 2026), a la home y a "Respuestas" en `/practicas/`, con crédito de Nicolás. El texto de "De dónde sale" son dos frases del texto del post, que ya estaban validadas. Aclara que la imagen está hecha con IA generativa.

**Razón:** Una convocatoria vacía no invita. Quien inicia responde primero.

---

### Decisión: Volante para imprimir

**Contexto:** La Práctica #01 circuló por LinkedIn e Instagram y no tuvo respuestas.

**Decisión:** `/practicas/volante/`: una hoja A4 o carta, a una tinta, con la pregunta, la consigna en tres párrafos cortos, un QR y tiras para arrancar. Cada persona de la red la imprime y la pega donde vive.

**Razón:** Los volantes callejeros son referencia del sistema de marca desde enero y hasta ahora no había ninguno. Saca la práctica de las redes y la lleva al lugar desde donde se pide responder. Cada volante pegado es además una foto para la bitácora.

---

### Decisión: El remiendo a la vista

**Contexto:** El manifiesto se declara documento vivo y el pilar 3 celebra la reparación visible. El sitio no mostraba cuándo ni cómo cambiaba. Nicolás pidió que se lo explicaran antes de decidir.

**Opciones consideradas:**
1. La fecha del último cambio y un link al historial en GitHub
2. Solo la fecha
3. Nada

**Decisión:** Opción 1. Cada página dice al pie "Último remiendo:" con la fecha, y "Ver historial" abre la lista de cambios de ese archivo. La nota del manifiesto suma "Proponé un cambio", que abre un mail.

**Razón:** El repositorio ya es público: el historial existe, faltaba mostrarlo. Al lado de "Est. 2025", una fecha reciente dice que el Lab se mueve. El costo está asumido: la fecha se cambia a mano con cada cambio de contenido o de diseño, y una fecha vieja juega en contra. El link deja a la vista los briefs y que el sitio se arma con Claude: es coherente con "conocimiento como bien común".

---

### Decisión: "MUNDANIDAD" entra completa

**Contexto:** Estaba en pendientes: entre 601 y unos 1420 px de ancho la palabra se cortaba por la derecha. A 1280 px se leía "MUNDANIDA".

**Decisión:** Es un bug y se corrige. El tamaño del logo sale del ancho de la ventana: `clamp(2.6rem, calc(11.3vw - 5px), 10rem)`. En la home el logo pasa a ser el `<h1>` de la página, que no tenía.

**Razón:** Un sangrado deliberado no deja la palabra a una letra de terminar.

---

### Decisión: Archivo Black sin negrita sintética

**Contexto:** Archivo Black tiene un solo peso. Los `h1`, `h2` y `h3` piden negrita y el navegador la inventaba engrosando la letra. Los títulos de las páginas internas se veían más gordos y empastados que el logo de la home.

**Decisión:** La fuente se declara para todo el rango de pesos: `font-weight: 400 900`.

**Razón:** Los títulos vuelven a verse como la marca. Es una línea de CSS.

---

### Decisión: En Prácticas, texto negro sobre coral

**Contexto:** El botón "Enviar respuesta" heredaba el azul de los links: azul sobre coral, contraste 2.4:1. La pregunta de la práctica iba en coral sobre crema, 2.97:1.

**Decisión:** El botón lleva texto negro (5:1). La pregunta va en coral oscuro y un punto más grande.

**Razón:** Es el botón por el que entra una respuesta. `BRAND.md` ya indicaba coral oscuro para texto coral sobre fondos claros.

---

### Decisión: El mapa de la red con nombres e hilos, no

**Contexto:** Alambre propuso abrir `/red/` con el continente de la marca como mapa: el nombre de cada persona sobre su ciudad de origen y un hilo azul hasta donde vive hoy.

**Decisión:** No en esa forma. `/red/` queda como estaba.

**Razón:** Nicolás: "Ahora somos 5 pero si se suman más queda feo." Con quince personas los nombres se pisan y los hilos hacia Europa se vuelven una maraña. Un mapa de la red tiene que aguantar que la red crezca.

Se rehízo el mismo día: ver la decisión que sigue.

---

### Decisión: El mapa de la red, con un punto por persona

**Contexto:** La versión con nombres e hilos no aguantaba que la red creciera.

**Opciones consideradas:**
1. No poner mapa
2. Un punto por persona sobre el continente, como portada de la página, con las fichas abajo
3. Lo mismo, con el mapa fijo al costado de la lista

**Decisión:** Opción 3. `/red/` muestra el continente de la marca con un punto por persona. Negro: vive ahí. Azul: salió de ahí, y el punto va en su ciudad de origen. Sin nombres, sin hilos y sin leyenda. Cada punto es un link a la ficha. Desde 700 px de ancho la lista va a la izquierda y el mapa a la derecha, fijo mientras se recorren las fichas. Un sticker amarillo sobre el Pacífico pregunta "¿Y vos, desde dónde?" y abre el mail para sumarse.

**Razón:** Se probó con treinta y un puntos y se sigue leyendo. Al costado de la lista el mapa trabaja de índice: queda a la vista mientras se recorren las fichas y cada punto lleva a su persona. Además deja entrar las primeras fichas en la primera pantalla; como portada, las mandaba abajo. Los colores de los puntos son los de los rótulos de los grupos (LATAM en negro, Diáspora en azul), por eso no lleva leyenda.

El costo: las fichas quedan en una columna más angosta y la lista es más larga. Si la red pasa de unas veinte personas va a hacer falta una ficha más compacta.

Cómo se suma un punto: `MAPA.md`.

---

### Decisión: Los commits van directo a la rama por defecto

**Contexto:** Para esta actualización Alambre armó un prototipo, mostró capturas, publicó una vista previa y abrió un PR para que Nicolás aprobara antes de publicar.

**Decisión:** Nicolás: "Necesito hacer todos los commits acá, no hace falta que armes borradores para que vea." Los cambios se commitean directo en `claude/setup-imprenta-framework-V4MJF`, que es la rama desde la que se publica el sitio. Sin PR ni vista previa.

**Razón:** Menos pasos. Nicolás revisa sobre el sitio publicado y lo que no le cierra se corrige con otro commit. Sigue valiendo que el qué lo decide él: Alambre no sube nada que no haya pedido o aprobado.

---

## 2026-10-07 — Código: limpieza de todo el repo

Nicolás pidió leer, interpretar, borrar, editar y optimizar el código de todo el repo. La condición la puso Alambre: que el sitio se vea igual que antes.

### Decisión: Se ordena el código sin cambiar cómo se ve el sitio

**Contexto:** `style.css` había crecido por capas. Cada pedido sumó reglas al final y varias pisaban a otras de más arriba. El azul de los links estaba escrito a mano doce veces y la tipografía de los títulos, treinta y cuatro.

**Decisión:** La hoja se reescribió entera en un orden fijo: variables, fuentes, base, piezas compartidas, cada página e impresión. Lo que se repetía pasó a una sola regla (recuadro, botón sticker, pieza pegada, link de texto, link de nota). Los colores y las dos tipografías se usan por variable. Se borró lo que no hacía nada: reglas que otra pisaba, selectores sin elemento, clases sin regla, los `role` que repetían lo que la etiqueta ya dice y una fuente que ninguna página cargaba. No se tocó ningún texto, ninguna medida y ningún color.

**Cómo se comprobó:** Con capturas de las ocho páginas antes y después, a 22 tamaños de ventana y a doble densidad con el ruido de impresión, comparadas píxel por píxel. Lo mismo con cada link y cada botón con el cursor encima y con el foco, con las anclas, con "De dónde sale" abierto y con cada página impresa a PDF. Además se comparó el estilo calculado de cada elemento, propiedad por propiedad, a siete anchos.

Después se repitió todo con contenido de prueba sumado a las páginas: más personas y más puntos, más artefactos, otra práctica, links y listas donde hoy no hay. Sirve para saber que lo que se publique más adelante también se va a ver como se habría visto con la hoja anterior. Y lo revisó un segundo agente que no había visto el trabajo.

Dio igual en todo, salvo cuatro cosas que hoy no cambian lo que se ve:

- El botón de "Cierre con llamado" (`.cta-link`) anima solo el color del fondo y el del borde. Antes animaba todas las propiedades, y las únicas que cambian son esas dos.
- Las tarjetas de los pilares ya no llevan `position: relative`. No tenían adentro nada que lo usara.
- La inclinación de los artefactos en la bitácora: ver la decisión que sigue.
- Las fotos de las fichas y la imagen del ejemplo en `/practicas/`, que se achicaron y se compararon aparte: ver "Imágenes del tamaño en que se ven".

Lo que queda fuera de esa comparación: una pieza usada fuera de su página, como una tarjeta de pilar en la home o el botón de enviar fuera de una práctica. Ahí la hoja nueva le da el aspecto que la pieza tiene hoy en su página. La anterior no siempre lo hacía.

Lighthouse da las mismas notas que antes en las ocho páginas, con una diferencia que no es un problema nuevo: en `/red/`, accesibilidad pasa de 96 a 95. Al sacar los `role` repetidos, tres controles de ARIA que aprobaban por tenerlos dejan de aplicar, y el único aviso que ya había (dos puntos del mapa muy juntos, ver `MAPA.md`) pesa más en la cuenta.

**Razón:** En una hoja donde cada cosa está una sola vez, se cambia una página sin romper otra. Quedaron 214 reglas de 246 y 716 declaraciones de 853. Comprimida pesa 0,7 KB más que antes (8,7 contra 8,1), porque ahora cada bloque dice qué es y dónde se usa.

---

### Decisión: Los nombres dicen dónde se usa cada cosa

**Contexto:** El header de todas las páginas se llamaba `manifiesto-header` y el footer, `contacto`. Prácticas y volante usaban clases `bitacora-*`. Los nombres venían de cuando cada pieza estaba en una sola página.

**Decisión:** Se renombraron. Los `id` y las anclas no cambiaron.

| Antes | Ahora |
|-------|-------|
| `manifiesto-header` | `site-header` |
| `contacto` | `site-footer` |
| `logo logo-small` | `logo` |
| `manifiesto-content`, `manifiesto-title`, `manifiesto-section`, `manifiesto-cierre` | `documento`, `documento-titulo`, `documento-seccion`, `documento-cierre` |
| `cta-marco` | `cta-cierre` |
| `bitacora-page`, `bitacora-content` | `pagina`, `pagina-contenido` |
| `bitacora-title`, `red-page-title` | `pagina-titulo` |
| `bitacora-intro`, `bitacora-intro-cont` | `pagina-intro`, `pagina-intro-sigue` |
| `manifiesto-page`, `red-page`, `practitioner-img`, `practitioner-info` | Se sacaron: no hacían falta |

**Razón:** Quien llega al código busca el header por "header", no por "manifiesto". La lista de piezas compartidas y dónde se usa cada una está en `SITE-STRUCTURE.md`.

---

### Decisión: En la bitácora, los artefactos se inclinan una vez para cada lado

**Contexto:** La regla anterior inclinaba hacia la derecha a las entradas pares de cada año, fueran artefactos o texto. Con una entrada de texto entre dos artefactos, los dos quedaban para el mismo lado. Además, un artefacto inclinado a la derecha no se enderezaba con el cursor encima, como pide `BRAND.md`.

**Decisión:** La cuenta se hace solo entre artefactos, y todos se enderezan.

**Razón:** Hoy no cambia nada, porque cada año tiene un solo artefacto. Se va a notar cuando haya dos en el mismo año. En Chrome y Firefox anteriores a mediados de 2023 la regla nueva no existe: ahí todos los artefactos quedan inclinados hacia la izquierda.

---

### Decisión: El sitio se publica sin Jekyll

**Contexto:** GitHub Pages pasaba el repo por Jekyll antes de publicarlo (figura en el registro de cada publicación), aunque el sitio es HTML escrito a mano. Jekyll convierte los `.md` en páginas: lo esperable es que `BRAND.md`, `DECISIONS.md` y los briefs estuvieran publicados en el dominio como páginas, con el tema de GitHub. No se pudo abrir el sitio para verlo.

**Decisión:** Un archivo vacío en la raíz, `.nojekyll`.

**Razón:** Se publica lo que hay en el repo, archivo por archivo, que es lo mismo que se prueba antes de subir. Los `.md` quedan en el dominio como archivos de texto (por ejemplo `/BRAND.md`), sin página armada. Se siguen leyendo en GitHub.

---

### Decisión: La hoja de estilos lleva versión

**Contexto:** Al renombrar clases, quien tuviera guardado en el navegador el `style.css` anterior iba a ver el HTML nuevo sin estilos en el header y en el footer.

**Decisión:** Las páginas piden `style.css?v=2`. El número sube cada vez que un cambio renombra o saca clases.

**Razón:** Para el navegador una dirección nueva es un archivo nuevo, y no usa el que tenía guardado.

---

### Decisión: Imágenes del tamaño en que se ven

**Contexto:** Las fotos de las fichas medían 500 x 500 px y se muestran a 80 x 80. En `/practicas/`, el afiche del ejemplo bajaba siempre a 1060 px de ancho y se ve, como mucho, a 416.

**Decisión:** Las fotos pasan a 240 x 240 y conservan el fondo transparente. El ejemplo usa los dos tamaños que ya estaban en el repo, con `srcset`, igual que en la bitácora.

**Razón:** Las cinco fotos pasan de 120 KB a 48 KB y alcanzan para pantallas de triple densidad. El ejemplo, en una pantalla común, baja de 123 KB a 60 KB. La salvedad: el archivo de 640 px no tiene exactamente la proporción del grande, así que la imagen mide 0,2 px distinto de alto y lo que sigue en esa página se corre menos de 1 px.

---

### Decisión: El video de prácticas responde al teclado como un botón

**Contexto:** El link del video se anuncia como botón a los lectores de pantalla, pero no respondía a la barra espaciadora. Al arrancar el video, el foco del teclado se perdía.

**Decisión:** Arranca también con la barra espaciadora y el foco pasa al reproductor.

**Razón:** Si se anuncia como botón, se tiene que portar como un botón.

---

### Decisión: La letra base sigue fija en 16 px

**Contexto:** `html { font-size: 16px }` no acompaña a quien configuró una letra más grande en su navegador. Se probó `100%`, que sí la acompaña.

**Decisión:** Queda en 16 px.

**Razón:** Con la letra del navegador en 20 px, en un teléfono angosto se cortan "MUNDANIDAD" y "MANIFIESTO". En 24 px se cortan en casi cualquier teléfono y, en la bitácora, la ficha del artefacto queda en una columna de 85 px. El zoom del navegador funciona bien. Para acompañar la letra configurada hay que volver a medir esos tamaños: queda en pendientes.

---

## 2026-10-07 — Red: las fichas van por orden alfabético

### Decisión: Dentro de cada grupo, por apellido

**Contexto:** Las fichas estaban en el orden en que cada persona se sumó. Al entrar Lucía Guedes, Nicolás pidió ordenarlas por abecedario en LATAM y en Diáspora. Alambre las ordenó primero por nombre y Nicolás lo corrigió: van por apellido.

**Decisión:** En cada grupo las fichas van por orden alfabético de apellido: Guedes, Latorre, Viadest; Bronzina, De la Mora, Gastaldy. "De la Mora" va en la D, como está escrito. Los puntos del mapa siguen el mismo orden.

**Razón:** El orden de llegada se puede leer como jerarquía. El abecedario no dice nada de nadie y deja claro dónde va la próxima persona.

---

## 2026-10-08 — Footer: las redes del Lab

### Decisión: Instagram y LinkedIn van en el footer, como texto

**Contexto:** El sitio no enlazaba a las redes del Lab. Nicolás pidió sumarlas al footer.

**Decisión:** Un renglón debajo de "Charlemos →" con el nombre de cada red, en la tipografía de las etiquetas y con el subrayado coral del link de nota. Va en las ocho páginas. Sin íconos: el sitio no usa ninguno y el nombre se lee igual.

En la home y en la 404, donde el footer es una fila, las redes son un elemento más de la fila. Esa fila ahora necesita unos 960 px: entre 601 y 960 el remiendo baja a un segundo renglón. Hasta 600 px sigue en columna centrada, como antes.

**Razón:** Quien llega al sitio y quiere seguir al Lab no tenía cómo. El footer es donde se busca eso y ya tenía el contacto.

---

## Decisiones Pendientes

- [x] Dominio propio → `mundanidadforzada.org` está activo (ver `CNAME`)
- [ ] Email con dominio propio
- [x] Contenido real de practitioners (nombres, bios, fotos) → cinco fichas en `/red/`
- [x] Imagen OG para redes sociales → reemplazada el 7 oct 2026
- [x] ¿Agregar año de fundación en algún lugar visible? → Decidido: sí, en footer ("Est. 2025")
- [ ] ¿El continente entra al header (`.logo`) o al poster de la home? Hoy es solo ícono
- [x] Retirar `img/lab-icon.png` (ícono anterior, 1 MB, sin referencias en el sitio) cuando los avatares de redes estén cambiados → retirado el 7 oct 2026: Nicolás confirmó que ya los cambió. Queda en el historial del repo
- [x] En la home, "MUNDANIDAD" se cortaba por la derecha entre 601 y unos 1420 px → bug, corregido el 7 oct 2026
- [ ] La descripción de la red nombra Uruguay ("Argentina, Brasil, México, Uruguay y contando") y en `/red/` no hay nadie de Uruguay
- [x] Mapa de la red, segunda versión: un punto por persona sobre el continente, sin nombres ni hilos → publicado el 7 oct 2026
- [x] La pieza pegada en la home. Al verla publicada, Nicolás preguntó qué aporta → se queda, decidido el 7 oct 2026 (ver "La home lleva pegado el último artefacto")
- [ ] Probar en Firefox y Safari que el mapa de `/red/` queda fijo al recorrer las fichas. Se probó en Chromium
- [ ] Imprimir el volante desde Firefox y Safari. Se probó en Chromium, en A4 y en carta
- [ ] En el manifiesto, las tarjetas de los pilares tienen 56 px de aire arriba del título y 24 px debajo del texto. En el marco, las mismas tarjetas tienen 24 px arriba. La limpieza lo dejó como estaba
- [ ] En el manifiesto, las cajas de "Marcos teóricos" están separadas por 28 px y las de "Principios organizativos" por 8 px
- [ ] En `/red/`, el link de cada ficha pasa a coral oscuro con el cursor encima. Los demás links de texto del sitio pasan a negro
- [ ] La flecha "→" no está en los archivos de fuente del sitio y aparece 26 veces ("Charlemos →", "LinkedIn →"). Cada dispositivo la dibuja con su propia tipografía. Archivo Black y Space Grotesk la traen: habría que volver a generar los archivos con la flecha adentro. Aparte, en el teléfono a veces queda sola en el renglón de abajo ("Ver en la bitácora" y la flecha en otra línea): se arregla pegándola a la palabra anterior
- [ ] Que la letra acompañe el tamaño configurado en el navegador. Ver "La letra base sigue fija en 16 px"
- [ ] La nota que abre el manifiesto y el marco estaba pensada más chica (0,9 rem) y con más aire debajo (3 rem). Nunca se vio así: la pisaba la regla de los párrafos. Se ve del tamaño del texto (1,1 rem). La limpieza sacó las dos líneas que no aplicaban
- [ ] Las cajas de "Marcos teóricos" y "Principios organizativos" estaban pensadas con 1 rem de relleno. Se ven con 0,5 rem arriba y abajo y sin relleno a la derecha, así que el texto llega al borde de la caja. Por lo mismo: la regla de las listas pisaba a la de las cajas
- [ ] El logo del header estaba pensado en una línea. Siempre se vio en tres

---

*Documento vivo. Se actualiza con cada decisión relevante.*
