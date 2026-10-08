# Glovo, medido contra su propia declaración de accesibilidad

**[Leer el informe completo](https://noxquality.github.io/glovo-eaa-check/informe.html)**  ·  [English](README.md)

> **Medición independiente y no solicitada, del 8 de octubre de 2026.** No está afiliada a
> Glovo ni aprobada por Glovo. Mide el producto público, tal como lo encuentra cualquiera
> que entra sin cuenta. No mide equipos, no mide personas, y ninguna falla se atribuye a
> nadie.

Glovo publicó una declaración de accesibilidad y se comprometió por escrito con WCAG 2.1
nivel AA y EN 301 549. Es el estándar con el que se mide accesibilidad en Europa, así que
es el que se usa acá.

Las cinco promesas concretas de ese documento se buscaron en el producto, una por una.

## Las cinco promesas

| La promesa, textual | Veredicto | Qué lo sostiene o lo rompe |
|---|---|---|
| Contraste suficiente entre texto y fondo | ✅ se sostiene | 1 fallo sobre 776 nodos medidos |
| Navegación sencilla, títulos y puntos de referencia | ✅ se sostiene | Faltan el enlace para saltar al contenido y el título de dos páginas |
| Notificaciones de error claras y descriptivas | 🟡 a medias | El error de opciones obligatorias no se anuncia |
| Accesibilidad del teclado | ❌ no se sostiene | El campo de dirección del home no se opera con teclado |
| Etiquetas accesibles en elementos interactivos | ❌ no se sostiene | 40 de 40 inputs del diálogo de producto sin nombre accesible |

El canal que la declaración ofrece para avisar de un problema, soporte, no se abre sin
cuenta: el enlace "Contact us" del pie es un ancla que no dispara nada.

## Dos hallazgos fuera de la declaración

**El arreglo llegó a restaurantes y no a tiendas.** Con una categoría entera cerrada, el
mismo local cerrado se comporta de dos maneras distintas según su vertical.

**La búsqueda contesta cualquier cosa con el mismo catálogo.** Buscar "motosierra" devuelve
el 69% de los mismos locales que buscar "pizza", con el mismo primer resultado.

## Qué hay en este repo

| archivo | qué es |
|---|---|
| [informe.html](informe.html) | el informe completo, con la evidencia de cada punto |
| [report.html](report.html) | el mismo informe en inglés |
| [evidencia/busqueda.md](evidencia/busqueda.md) | la batería de siete consultas de búsqueda, con el método y el cálculo |

## Método y límites, en corto

Web desktop, Barcelona, sin login, cookies denegadas, cuatro páginas más dos diálogos.
Inspección del DOM y del árbol de accesibilidad, recorrido con teclado contado Tab por Tab,
y contraste calculado sobre color y fondo computados.

No se midió con lector de pantalla real, ni la app nativa, ni el checkout, que exige cuenta.
Los límites completos están en el informe.

Esta pieza **no hace un reclamo legal**. Si una empresa cumple o incumple una norma lo
decide un organismo, no una auditoría privada.

## Licencia y autoría

Texto y datos bajo [CC BY 4.0](LICENSE). Hecho por
[Nox Quality Studio](https://noxquality.com), by sol.
