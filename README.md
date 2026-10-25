# Tokimeki Memorial ~Densetsu no Ki no Shita de~ (Super Nintendo) — Traducción al español

[![Invítame a un café en Ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/johanderohan)

Traducción al **español de España** de *Tokimeki Memorial ~Densetsu no Ki no Shita de~*
(Super Famicom, Konami, 1996), el simulador de citas en el que pasas tres cursos en el
Instituto Kirameki esperando que, el día de la graduación, una chica se te declare bajo el
árbol de la leyenda. Se ha traducido **directamente del japonés**, a partir de la ROM japonesa
original (Rev 1).

La traducción se reparte como **parche**: no incluye el juego. Necesitas tu propia copia para
aplicarlo.

## Estado

Última versión: **[v1.0 — Primera versión completa](../../releases/tag/v1.0)** (en revisión).

| Parte | Estado |
|---|---|
| Guion de escenas (todas las chicas, citas, eventos, festivales, viajes, finales y epílogo) | **22.689 mensajes** (18.812 distintos) traducidos y revisados |
| Texto de sistema: menús, calendario, teléfono, revista, minijuegos, festival cultural, combate, créditos y **declaraciones finales** | **1.124 cadenas** traducidas y revisadas |
| Entrada de nombre | Rejilla nueva con letras latinas: **á é í ó ú ü ñ** y mayúsculas |
| Rótulos gráficos necesarios para jugar | Título (EMPEZAR / OPCIONES), panel de fecha (AÑO / MES / DÍA y días de la semana), géneros de la revista |
| Caracteres españoles | **á é í ó ú ü ñ Á É Í Ó Ú Ü Ñ ¡ ¿ « » “ ” …** |
| Logotipos y rótulos de marca | Se conservan (ver abajo) |
| Revisión durante una partida | Comienzo de partida, primeros meses, citas, festivales, finales y epílogo vistos en el juego (ver abajo) |

Se mantienen a propósito, como imagen de marca, el logotipo del título, el cartel del Instituto
Kirameki y la cabecera de la revista «Memorial Spot».

### Cambios técnicos

- El juego dibuja el texto en casillas fijas de 16 píxeles pensadas para kanji. Se ha añadido una
  **fuente de ancho variable** con el mismo trazo, color y sombra que la original (hecha a partir
  de las propias letras latinas de la fuente del juego) y una **fuente estrecha** para las
  pantallas de baja resolución (epílogo, declaraciones, combate). Se conservan el efecto de máquina
  de escribir, las pausas y los cambios de expresión.
- El cuadro de diálogo se ha reorganizado para que quepa el nombre del personaje en castellano
  (se muestra el nombre de pila: los apellidos no cabían en el espacio del original) y el texto
  se corta en renglones por palabras completas.
- Todo el guion se ha reempaquetado en la ROM con una compresión por diccionario nueva para el
  castellano: **la ROM sigue midiendo 4 MB**, como el original.
- La rejilla para escribir el nombre, el apellido y el apodo se ha rehecho con letras latinas.

### Comprobaciones y trabajo pendiente

- Una auditoría automática relee la ROM construida y comprueba cada mensaje del guion (que el
  juego lo encuentra donde debe), cada cadena de sistema y sus referencias, los diccionarios y el
  *checksum* interno.
- Probado en emulador (snes9x) **desde partida nueva**: título y opciones, álbum, rejilla de
  nombres con tildes y eñes, prólogo completo, menú principal y sus órdenes, clubes, teléfono,
  calendario, invitaciones y citas con elecciones, revista, guardar y cargar, festivos, la jornada
  deportiva (pruebas e instrucciones), el festival cultural (teatro y discurso), varias
  declaraciones finales completas y el epílogo en varias combinaciones. Arranque comprobado
  también en bsnes (modo de precisión). En total, varias rondas de QA con capturas revisadas.
- **Pendiente:** una partida completa jugada de principio a fin (no se han visto en pantalla los
  exámenes, el segundo y tercer curso enteros, todas las declaraciones y epílogos ni los créditos),
  la prueba en consola física o *flashcart* y una revisión humana independiente. La traducción y
  su revisión se han hecho con asistencia de IA. Por eso la versión figura «en revisión»; si
  encuentras algo, abre una incidencia.

### Incidencias conocidas

- Algunos carteles y bocadillos dibujados siguen en japonés (cabecera y número de la revista,
  letreros de la jornada deportiva…); los días de la semana del calendario de citas están en
  inglés, como en el original.
- Abreviaturas en la confirmación del nombre («Nbre.», «Cump.») y en algunos menús muy estrechos;
  los recuadros de selección de las opciones del título no siempre cubren la palabra entera.
- El texto del epílogo se ve con poco contraste (como en el original).
- Las partidas guardadas con la versión japonesa pueden mostrar mal el nombre del protagonista:
  conviene empezar partida nueva.

## Cómo aplicar el parche

1. Descarga el parche `.xdelta` de la sección **[Releases](../../releases)**.
2. Consigue tu copia del juego en versión **japonesa, revisión 1** (Rev 1). El parche solo
   funciona con esa versión exacta, sin cabecera de copiadora:

   | | |
   |---|---|
   | Archivo | `Tokimeki Memorial - Densetsu no Ki no Shita de (Japan) (Rev 1).sfc` |
   | Tamaño | 4.194.304 bytes (4 MB) |
   | MD5 | `cd36eb8982de4bf8369deb9f2f23e590` |
   | CRC32 | `AE9F3602` |

   ```bash
   md5sum "Tokimeki Memorial - Densetsu no Ki no Shita de (Japan) (Rev 1).sfc"     # Linux
   md5 "Tokimeki Memorial - Densetsu no Ki no Shita de (Japan) (Rev 1).sfc"        # macOS
   CertUtil -hashfile "Tokimeki Memorial - Densetsu no Ki no Shita de (Japan) (Rev 1).sfc" MD5   # Windows
   ```

   Si tu archivo mide 4.194.816 bytes tiene una cabecera de 512 bytes: quítala antes de
   parchear. Si el MD5 no coincide (por ejemplo, con la primera edición, sin «Rev 1»), el parche
   fallará.
3. Aplica el parche con una de estas herramientas:
   - **Windows**: [Delta Patcher](https://github.com/marco-calautti/DeltaPatcher/releases)
   - **Linux / macOS**: `xdelta3 -d -s "Tokimeki Memorial - Densetsu no Ki no Shita de (Japan) (Rev 1).sfc" tokimeki-memorial-snes-es-v1.0.xdelta "Tokimeki Memorial (ES).sfc"`
4. Comprueba que la ROM resultante mide **4.194.304 bytes** y tiene MD5
   **`dc4adee39ca5a396aeee823198b2f220`**.
5. Juega en tu emulador o *flashcart*. El juego guarda en la memoria del cartucho (dos álbumes).

## Cambios por versión

### v1.0 — 27 de octubre de 2026

- Primera versión completa: todo el guion, los menús, el teléfono, la revista, los minijuegos,
  el festival cultural, las declaraciones finales y el epílogo en castellano de España,
  traducidos del japonés.
- Fuente española de ancho variable con el estilo original, fuente estrecha para las pantallas de
  baja resolución, rejilla de nombres con letras latinas y rótulos del título y del calendario
  traducidos.

## Aviso

Este proyecto es una traducción hecha por afición, sin ánimo de lucro y sin relación alguna con
Konami ni con los titulares de *Tokimeki Memorial*. Aquí no se distribuye el juego ni ninguna
parte de él: solo un parche que modifica una copia que ya tengas.

Si eres el titular de los derechos y quieres que retire esto, abre una incidencia y lo hago.
