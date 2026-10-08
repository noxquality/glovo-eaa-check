# Evidencia: la batería de consultas de búsqueda

Medido el **8 de octubre de 2026**, entre las 03:10 y las 03:45, hora de Barcelona.

## Condición

- Glovo web desktop, `glovoapp.com/en/es/barcelona`
- Dirección cargada: Carrer de Balmes, 100
- Sin login
- Cookies denegadas en el banner

## Método

Para cada consulta:

1. Navegación directa a `https://glovoapp.com/en/es/barcelona/search?q=<consulta>`
2. Cuatro segundos de espera
3. Conteo de los hijos de `ul[class*="SearchResults_wrapper"]`
4. Extracción del nombre de cada local desde `h3` o `[class*="titleWrapper"]` de cada `li`
5. Búsqueda del texto "No results" en el cuerpo de la página

El mismo método en las siete consultas, sin scroll adicional. El listado corta en 100, así
que "100" quiere decir "el tope, puede haber más detrás del scroll". La comparación entre
consultas se sostiene igual porque el recorte es el mismo para todas.

## Resultados

| consulta | qué es | resultados | "No results" | primeros cinco locales |
|---|---|---|---|---|
| `pizza` | control, producto real | 100 (tope) | no | Domino's Pizza, ARTBAGUETTE, Rovica Tapas, El Súper de Glovo, Bracafe 1929 |
| `motosierra` | palabra real, producto que Glovo no reparte | 100 (tope) | no | Domino's Pizza, Rovica Tapas, Restaurante Teruel, Mezza Morris, Fnac |
| `aeiouaeiou` | sin sentido, letras comunes | 100 (tope) | no | ARTBAGUETTE, Le Creps & Pancakes, Avocado Toast Bruch, Trie Bakery, EC Brunch |
| `qqqqqqqq` | sin sentido, una letra rara | 87 | no | VICIO, KFC, X Burger, Carl's Jr, California Chicken by Carl's Jr |
| `zzzqqqxyw` | sin sentido, letras raras | 20 | no | Can Xam&Pa, X Burger, Chivuo's, Chic Burger, Z&Co. Lebanese Deli |
| `uranio enriquecido` | dos palabras reales, producto absurdo | 0 | **sí** | — |
| `asdfghjkl` | manotazo de teclado | 0 | **sí** | — |

## El cálculo del solapamiento

Listas completas de `pizza` y de `motosierra`, 100 posiciones cada una, 99 locales únicos
cada una (una repetición en las dos: "Deep Detroit Style Pizza" aparece dos veces).

- Locales en las dos listas: **68**
- Solapamiento sobre el total de `motosierra`: **69%**
- Jaccard: **52%**
- Primer resultado de las dos consultas: **el mismo**, Domino's Pizza
- Resultados de `motosierra` con "pizz" en el nombre: **41 de 100**

Los 31 locales que aparecen solo en `motosierra`: Antonia's Burger, Casa Fernández, Casa
Moritz Barcelona, Creamy Homemade Pasta, Divan Turkish Restaurant, El Turco Bar Doner Kebab
Pizzería, Fnac, Frankfurt Sants, Frankfurt y Hamburgueseria El Sot, Fàbrica Moritz
Barcelona, Kebab & Curry Restaurant, Kebab Alcalde, Mando Huevos, Maur, Melosa
Hamburguesería, Mezza Morris, Mimmar, Monster Sushi, Morrita, Petit Muu, Pizzería El
Felino, Pollo Brasas, Restaurante Teruel, Rostisseria La Bombonera, Rostissería Xarcuters
Galobart, STAR KEBAB PIZZERIA, Sabores Express, Santa Gula, Sants XXL Kebab, Saona, Soco.

## Qué se concluye y qué no

**Se concluye** que el piso de relevancia de la búsqueda está lo bastante bajo como para
que una palabra que el catálogo no cubre devuelva el mismo conjunto de locales que una
consulta legítima.

**No se concluye** cómo está implementada la búsqueda. El patrón es compatible con una
búsqueda semántica sin umbral, pero eso es una hipótesis sobre la implementación y desde
afuera no se puede verificar.

**No se midió** si el comportamiento cambia con sesión iniciada, en otra ciudad o en la
app nativa.
