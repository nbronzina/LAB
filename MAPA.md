# Lab de Mundanidad Forzada — El mapa de la red

> Última actualización: 7 octubre 2026
> Dónde vive: `red/index.html` (bloque `.red-mapa`) y `style.css` (sección "RED - Mapa")

---

## Qué es

`/red/` muestra el continente de la marca usado como mapa, con un punto por persona. Es el mismo archivo que el ícono (`img/marca/continente-riso.svg`), sin redibujar: mismo territorio, misma proyección (Equal Earth centrada en 76° O), misma veta azul.

Cada punto es un link a la ficha de esa persona, en la misma página. En el mapa no hay nombres ni líneas: así aguanta que la red crezca. Se probó con treinta y un puntos.

Desde 700 px de ancho la lista va a la izquierda y el mapa a la derecha, fijo mientras se recorren las fichas. Es el índice de la lista. En pantallas más angostas va entre la introducción y las fichas.

## Cómo se lee

| En el mapa | Qué significa |
|------------|---------------|
| Punto negro | Vive ahí |
| Punto azul | Salió de ahí. Va en su ciudad de origen, porque el ancla del Lab es Latinoamérica |
| Sticker amarillo | "¿Y vos, desde dónde?". Abre el mail para sumarse |

El mapa no lleva leyenda. Los colores de los puntos son los de los rótulos de los grupos: LATAM en negro, Diáspora en azul. El azul es el color del desplazamiento en todo el sistema (ver `DECISIONS.md`, enero 2026).

El nombre aparece al pasar el cursor por un punto o al llegar con el teclado. En pantallas táctiles no hay cursor: tocar el punto lleva a la ficha.

## Accesibilidad

- Cada punto es un link con nombre. Un lector de pantalla lee "Miriam Latorre, Chivilcoy".
- Todo lo que está en el mapa está también en la lista. El mapa es un atajo, no la única forma de llegar.
- Los puntos de dos ciudades cercanas quedan a menos de 24 px uno del otro. Lighthouse lo marca como área de toque insuficiente y por eso `/red/` da 96 en accesibilidad. Es la excepción "esencial" de WCAG 2.5.8, que pone de ejemplo los pines de un mapa: la posición es la información. No se corrige separando los puntos más de lo que dice "Cuando dos ciudades se pisan".

---

## Sumar una persona

1. **Ficha.** Agregá el `<article class="practitioner-card" id="nombre-apellido">` en el grupo que corresponda (LATAM o Diáspora). El `id` va en minúsculas, sin tildes y con guiones.
2. **Punto.** Agregá un `<li>` en `<ul class="red-mapa-puntos">` con las coordenadas de su ciudad (tabla de abajo). Si la ciudad ya tiene su `<li>`, el punto nuevo va adentro de ese mismo `<li>`.
3. **Mirá el mapa a 390 px y a 1440 px.** Si dos ciudades se pisan o un punto de la costa cae sobre el mar, corrélo (ver "Cuando dos ciudades se pisan").
4. **Remiendo.** Actualizá la fecha al pie de la página y el `lastmod` de `/red/` en `sitemap.xml`.

### Vive ahí

```html
<li style="--x: 19.38%; --y: 15.05%"><a href="#israel-viadest" class="punto"><span class="punto-nombre">Israel Viadest<span class="solo-lector">, Querétaro</span></span></a></li>
```

### Salió de ahí

Las coordenadas son las de la ciudad de origen. La clase `punto--fue` lo pinta de azul.

```html
<li style="--x: 80.29%; --y: 65.33%"><a href="#renan-gastaldy" class="punto punto--fue"><span class="punto-nombre">Renan Gastaldy<span class="solo-lector">, de São Paulo a Valencia</span></span></a></li>
```

### Varias personas en la misma ciudad

Un solo `<li>` con un `<a>` por persona. Los puntos se apilan solos, de a tres por fila.

```html
<li style="--x: 66.09%; --y: 77.19%">
  <a href="#nicolas-bronzina" class="punto punto--fue"><span class="punto-nombre">Nicolás Bronzina<span class="solo-lector">, de Buenos Aires a Madrid</span></span></a>
  <a href="#otra-persona" class="punto"><span class="punto-nombre">Otra Persona<span class="solo-lector">, Buenos Aires</span></span></a>
</li>
```

### El texto de cada punto

En `.punto-nombre` va el nombre completo: es lo que se ve al pasar el cursor. Lo que sigue, dentro de `.solo-lector`, no se ve y lo lee un lector de pantalla: la ciudad, o "de (origen) a (donde está hoy)".

---

## Cuando dos ciudades se pisan

Chivilcoy y Buenos Aires están a 160 km: a escala del mapa es el mismo lugar. Se corre cada `<li>` unos píxeles con `--dx` y `--dy`:

```html
<li style="--x: 64.3%; --y: 77.5%; --dx: -5px">…</li>
<li style="--x: 66.09%; --y: 77.19%; --dx: 5px">…</li>
```

- No más de 8 px en total por ciudad.
- Las ciudades de costa (Lima, Valparaíso, Barranquilla) quedan justo en el borde del dibujo. Si el punto cae sobre el mar, corrélo tierra adentro.
- Si una zona junta muchas ciudades cercanas (el Río de la Plata, el centro de México), que los puntos se toquen está bien: se lee como concentración. Lo que no puede pasar es que uno tape entero a otro.

---

## Coordenadas

`--x` y `--y` son la posición de la ciudad en porcentaje del encuadre del mapa.

El encuadre, en las unidades del continente L, va de X −20 a 750 y de Y −20 a 1036 (770 × 1056). El continente ocupa de 0 a 714 en X y de 0 a 1000 en Y. El archivo `continente-riso.svg` mide 730.4 × 1015.7 con la veta azul, y por eso en el CSS va a `left: 2.6%`, `top: 1.89%` y `width: 94.86%`.

**México y Centroamérica**

| Ciudad | `--x` | `--y` |
|--------|-------|-------|
| Tijuana | 2.59% | 2.08% |
| Monterrey | 19.94% | 9.42% |
| Guadalajara | 16.01% | 14.96% |
| Querétaro | 19.38% | 15.05% |
| Ciudad de México | 20.72% | 16.35% |
| Puebla | 21.74% | 16.78% |
| Oaxaca | 23.31% | 19.00% |
| Mérida | 31.70% | 14.63% |
| Ciudad de Guatemala | 30.37% | 21.76% |
| San Salvador | 31.87% | 22.83% |
| Tegucigalpa | 34.20% | 22.39% |
| Managua | 35.24% | 24.63% |
| San José | 37.72% | 27.12% |
| Panamá | 43.05% | 28.21% |

**Caribe**

| Ciudad | `--x` | `--y` |
|--------|-------|-------|
| La Habana | 39.96% | 12.25% |
| Puerto Príncipe | 51.35% | 17.29% |
| Santo Domingo | 54.12% | 17.42% |
| San Juan | 58.49% | 17.42% |

**Sudamérica, norte y Andes**

| Ciudad | `--x` | `--y` |
|--------|-------|-------|
| Caracas | 57.77% | 26.48% |
| Maracaibo | 52.24% | 26.29% |
| Barranquilla | 48.56% | 25.92% |
| Cartagena | 47.73% | 26.59% |
| Medellín | 47.66% | 31.34% |
| Bogotá | 49.42% | 33.12% |
| Cali | 46.54% | 34.57% |
| Quito | 44.26% | 38.76% |
| Guayaquil | 42.59% | 41.08% |
| Lima | 45.95% | 52.41% |
| Cusco | 51.83% | 54.09% |
| Arequipa | 52.30% | 57.36% |
| La Paz | 56.20% | 57.46% |
| Cochabamba | 58.47% | 58.46% |
| Santa Cruz de la Sierra | 61.88% | 58.90% |

**Brasil**

| Ciudad | `--x` | `--y` |
|--------|-------|-------|
| Manaos | 65.93% | 42.15% |
| Belém | 79.47% | 40.24% |
| Fortaleza | 91.14% | 42.86% |
| Recife | 95.25% | 47.83% |
| Salvador | 90.69% | 53.46% |
| Brasilia | 79.61% | 56.66% |
| Belo Horizonte | 83.75% | 61.30% |
| Río de Janeiro | 84.28% | 64.63% |
| São Paulo | 80.29% | 65.33% |
| Curitiba | 77.11% | 67.40% |
| Florianópolis | 77.65% | 69.75% |
| Porto Alegre | 74.38% | 72.37% |

**Cono Sur**

| Ciudad | `--x` | `--y` |
|--------|-------|-------|
| Asunción | 67.81% | 67.21% |
| Salta | 59.05% | 66.70% |
| Tucumán | 59.17% | 68.90% |
| Córdoba | 60.07% | 73.85% |
| Mendoza | 54.92% | 75.40% |
| Rosario | 63.80% | 75.47% |
| Chivilcoy | 64.30% | 77.50% |
| Buenos Aires | 66.09% | 77.19% |
| La Plata | 66.52% | 77.52% |
| Mar del Plata | 66.60% | 80.68% |
| Neuquén | 55.48% | 81.64% |
| Bariloche | 52.01% | 83.81% |
| Ushuaia | 54.32% | 96.38% |
| Montevideo | 68.44% | 77.50% |
| Antofagasta | 53.47% | 65.44% |
| Valparaíso | 51.90% | 75.57% |
| Santiago | 52.92% | 75.99% |
| Concepción | 50.29% | 79.49% |
| Punta Arenas | 51.95% | 94.99% |

### Una ciudad que no está en la tabla

Con longitud y latitud en grados (oeste y sur, negativos):

```
d  = lon + 76              (si d > 180, restale 360; si d < −180, sumale 360)
λ  = d · π / 180
φ  = lat · π / 180
θ  = asin(0.8660254 · sin φ)

ex = λ · cos θ / (0.8660254 · (1.340264 − 0.243318·θ² + θ⁶ · (0.006251 + 0.034164·θ²)))
ey = θ · (1.340264 − 0.081106·θ² + θ⁶ · (0.000893 + 0.003796·θ²))

X  =  601.7607 · ex + 343.130
Y  = −601.7607 · ey + 387.097

--x = (X + 20) / 770  · 100
--y = (Y + 20) / 1056 · 100
```

Para comprobar la cuenta: Buenos Aires (−58.38, −34.60) da X 488.9, Y 795.1, `--x` 66.09%, `--y` 77.19%.

Es la proyección Equal Earth (Šavrič, Patterson y Jenny, 2018) con la escala y el desplazamiento que usa el archivo del continente.

---

## Lo que no se hace

- No se redibuja el continente para el mapa: se usa el archivo de la marca.
- No van nombres fijos sobre el mapa, ni líneas, ni flechas. Con cinco personas se veía bien y con quince no (ver `DECISIONS.md`).
- No se agrega leyenda, ni países, ni fronteras.
- No se dibuja el lugar donde vive hoy quien está en la diáspora. El mapa es el continente.
- No se mueve un punto para que "quede mejor". Solo el corrimiento de pocos píxeles cuando dos se pisan o uno cae sobre el mar.

---

*Documento vivo. Se actualiza cuando cambia el mapa.*
