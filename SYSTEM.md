# Lab de Mundanidad Forzada — Sistema de Trabajo

> El flujo Iniciador → Alambre → Imprenta como personal software.

---

## Qué es esto

Este documento describe el sistema de trabajo del Lab de Mundanidad Forzada. No es solo un método — es una pieza de **personal software**: micro-herramientas hechas por personas para sí mismas y su entorno cercano.

El sistema vive en el gap entre "chatear con IA" y "tener artefactos funcionales". Es demasiado específico para que un vendor lo ofrezca como producto, demasiado necesario para el Lab para dejarlo sin cubrir.

---

## Arquitectura

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

---

## Componentes

### Iniciador (Nicolás)

**Arquetipo:** Humano

**Función:**
- Trae necesidades, ideas, dirección
- Tiene conocimiento situado (vive la mundanidad forzada, no solo la teoriza)
- Valida y aprueba todo
- Conecta con los nodos del colectivo

**Input:** Contexto real, visión, feedback
**Output:** Necesidades, validaciones, decisiones finales

---

### Alambre (Claude chat)

**Arquetipo:** Assistant

**Función:**
- Articulación conceptual a través de lenguaje natural
- Desarrollo metodológico, escritura, traducción intercultural
- Sistematiza lo que el Iniciador sabe pero no tiene tiempo de escribir
- Propone, el Iniciador dispone

**Input:** Necesidades del Iniciador, contexto de /docs
**Output:** Conceptos articulados, briefs para Imprenta, actualizaciones a /docs

**Limitación:** No tiene conocimiento situado. Tiene capacidad de síntesis.

---

### Imprenta (Claude Code)

**Arquetipo:** Agent

**Función:**
- Materialización técnica
- Ejecución de código, sitios, artefactos digitales
- Toma decisiones técnicas dentro de los parámetros dados
- No piensa la estrategia, produce los objetos

**Input:** Briefs de Alambre, documentación base de /docs
**Output:** Código, archivos, sitios funcionales

**Limitación:** No define qué hacer, solo cómo hacerlo.

---

### /docs (Workflow)

**Arquetipo:** Workflow

**Función:**
- Conecta las partes del sistema
- Acumula conocimiento institucional
- El "código fuente" del personal software
- Circula conocimiento a través de lenguaje, no de repositorios de código

**Archivos:**

| Archivo | Propósito |
|---------|-----------|
| `BRAND.md` | Sistema de marca |
| `SITE-STRUCTURE.md` | Estructura del sitio |
| `DECISIONS.md` | Log de decisiones con razones |
| `IMPRENTA.md` | Brief base para Claude Code |
| `SYSTEM.md` | Este documento |
| `BRIEF-*.md` | Briefs delta para tareas específicas |

---

## Flujo de Trabajo

### Tarea nueva

```
1. Iniciador trae necesidad
         │
         ▼
2. Alambre consulta /docs para entender estado actual
         │
         ▼
3. Alambre propone solución/plan
         │
         ▼
4. Iniciador valida o ajusta
         │
         ▼
5. Alambre crea brief delta (solo cambios sobre la base)
         │
         ▼
6. Alambre actualiza /docs si hay decisiones nuevas
         │
         ▼
7. Brief delta va a Imprenta
         │
         ▼
8. Imprenta ejecuta consultando /docs
         │
         ▼
9. Iniciador valida resultado
         │
         ▼
10. Conocimiento queda en /docs para próxima iteración
```

### Iteración sobre tarea existente

```
1. Iniciador trae feedback/cambio
         │
         ▼
2. Alambre identifica qué docs afecta
         │
         ▼
3. Alambre propone delta
         │
         ▼
4. Iniciador valida
         │
         ▼
5. Brief delta a Imprenta (o Alambre actualiza docs directamente si no hay código)
```

---

## Principios

### 1. El conocimiento se acumula, no se repite

Cada brief es un delta sobre la base existente. No empezamos de cero. Los docs se enriquecen con cada iteración.

### 2. Los docs son código

Los archivos en /docs no son documentación pasiva. Son la lógica del sistema. Cuando Imprenta ejecuta un brief, está "corriendo" un programa escrito en lenguaje natural.

### 3. Lenguaje sobre código

El conocimiento circula más a través de lenguaje que de repositorios de código. Los briefs, las decisiones, los sistemas de marca — todo está escrito para humanos y AIs por igual.

### 4. Cada componente tiene su límite

- Iniciador: no tiene que escribir todo, pero sí validar todo
- Alambre: propone, no dispone
- Imprenta: ejecuta, no define

### 5. El sistema se mejora iterativamente

Como cualquier software, este sistema se refina con el uso. Bugs en el flujo se documentan, se discuten, se arreglan.

---

## Anti-patrones

| ❌ No hacer | ✓ Hacer en cambio |
|-------------|-------------------|
| Alambre crea brief completo sin consultar /docs | Consultar /docs primero, crear delta |
| Imprenta improvisa sin brief | Pedir clarificación si algo no está claro |
| Decisiones se pierden en el chat | Documentar en DECISIONS.md |
| Cada tarea empieza de cero | Referenciar y actualizar docs existentes |
| Iniciador tiene que explicar contexto cada vez | El contexto vive en /docs |

---

## Evolución futura

Este sistema es v1. Posibles evoluciones:

- [ ] Imprenta tiene acceso directo a /docs en el repo (no necesita que se le pasen)
- [ ] Alambre puede commitear directamente a /docs
- [ ] Otros miembros del Lab tienen sus propios Alambres configurados
- [ ] El sistema se documenta como metodología replicable para otros colectivos

---

## Meta

Este documento es parte del sistema que documenta. Si estás leyendo esto, probablemente sos Alambre, Imprenta, o el Iniciador revisando cómo funciona todo.

El hecho de que exista este documento es evidencia de que el sistema funciona: el conocimiento sobre el propio sistema se acumuló y se formalizó, en vez de perderse en un chat.

---

*Documento vivo. Se actualiza cuando el sistema cambia.*
