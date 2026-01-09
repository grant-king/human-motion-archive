## human-motion-archive
**EN**: A community archive of CC0 spritesheet images that are made from live recordings of human models in motion 

**ES**: Un archivo comunitario de imágenes en spritesheet con licencia CC0 hechas a partir de grabaciones en vivo de modelos humanos en movimiento

# Human Motion Archive — Public Domain Human Motion Spritesheets (CC0) // Spritesheets de humanos en movimiento con licencia CC0

**EN:** This repository is a monthly export of a public-domain, open-source human motion dataset: tiny, privacy-conscious dance/motion animations captured as pixel-art spritesheets.

**ES:** Este repositorio es una exportación mensual de un conjunto de datos de movimiento humano en dominio público y de código abierto: animaciones ligeras y cuidadosas con la privacidad, capturadas como hojas de sprites (pixel-art).

## What’s in here / Qué contiene

* **EN:** **WebP spritesheet images** organized by **date**, **sheet size** and **frame size** for easy machine analysis.

* **ES:** **Imágenes WebP** organizadas por **fecha**, **tamaño de hoja** y **tamaño de fotograma** para facilitar el análisis automático.

## Why spritesheets / Por qué hojas de sprites

* **EN:** Spritesheets are easy to parse, easy to cache, and stable across platforms.

* **ES:** Las hojas de sprites son fáciles de analizar, almacenar en caché y estables en todas las plataformas.

## License / Licencia

**EN:** All animations in this dataset are dedicated to the **public domain (CC0)**. You may use them for any purpose.

**ES:** Todas las animaciones de este conjunto están dedicadas al **dominio público (CC0)**. Puedes usarlas para cualquier propósito.

**EN:** See: [Creative Commons CC0](https://creativecommons.org/publicdomain/zero/1.0/) for more details.

**ES:** Ver: [Creative Commons CC0](https://creativecommons.org/publicdomain/zero/1.0/) para más detalles.

## How the dataset is created / Cómo se crea el conjunto de datos

**EN:** Animations are created with a camera-based recorder tool. Recording happens locally first; creators review the result and explicitly approve publishing. Approved animations are synced to a storage backend and exported here monthly as a static archive suitable for collaboration and mirroring.

**ES:** Las animaciones se crean con una herramienta de grabación usando cámara. Primero se graba localmente; el creador revisa el resultado y aprueba explícitamente su publicación. Las animaciones aprobadas se sincronizan con un backend de almacenamiento y se exportan aquí cada mes como un archivo estático apto para colaborar y replicar.

## Data format / Formato de datos

**EN:** Each file is a spritesheet:

* **Sheet size:** `N × N` pixels (from directory name, e.g. `1024_px`)
* **Frame size:** `F × F` pixels (from directory name, e.g. `64_px`)
* **Capture FPS:** `24 fps` (from directory name, e.g. `24_fps`)
* **Grid:** `(N/F) × (N/F)` frames
* **Order:** left → right, top → bottom

**ES:** Cada archivo es una hoja de sprites:

* **Tamaño de hoja:** `N × N` píxeles (del nombre del directorio, por ejemplo `1024_px`)
* **Tamaño de fotograma:** `F × F` píxeles (del nombre del directorio, por ejemplo `64_px`)
* **FPS de captura:** `24 fps` (del nombre del directorio, por ejemplo `24_fps`)
* **Cuadrícula:** `(N/F) × (N/F)` fotogramas
* **Orden:** izquierda → derecha, arriba → abajo

## Directory layout / Estructura de directorios

```
(EN) data/<year>/<month>/<sheet_px>/<frame_px>/<capture_fps>/*.webp
```

```
(ES) data/<año>/<mes>/<tamaño_hoja_px>/<tamaño_fotograma_px>/<fps_captura>/*.webp
```

Examples:

* `data/2026/01/1024_px/64_px/24_fps/*.webp`
* `data/2026/01/512_px/32_px/12_fps/*.webp`

## Tools & reference implementations / Herramientas y ejemplos

This repo also includes (or links to) simple reference tools:

* Recorder example / Ejemplo grabador: `tools/recorder-example` (or external repo)
* Player example / Ejemplo reproductor: `tools/player-example` (or external repo)

Related repos / Repos relacionados:

* Animation creation tool: (link)
* Backend storage service: (link)

## Contributing / Cómo colaborar

**EN:** Contributions are welcome—code, tools, documentation, and new capture pipelines. This dataset intentionally minimizes per-file metadata to keep the system lightweight; improvements should preserve that philosophy.

**ES:** Se agradecen contribuciones—código, herramientas, documentación y nuevas formas de captura. Este conjunto minimiza metadatos por archivo para mantener el sistema ligero; las mejoras deberían respetar esa filosofía.

Start here / Empieza aquí:

* `docs/CONTRIBUTING.md`

## Project goal / Objetivo del proyecto

**EN:** Dance and human motion are cultural artifacts. This project aims to preserve movement in a lightweight format that encourages reuse, study, and creative proliferation—while reducing personal detail. It is **not** designed for extreme privacy or strict ownership controls; publishing to the public domain is the point.

**ES:** La danza y el movimiento humano son artefactos culturales. Este proyecto busca preservar el movimiento en un formato ligero que facilite la reutilización, el estudio y la proliferación creativa—reduciendo el detalle personal. **No** está diseñado para privacidad extrema ni control estricto de propiedad; publicar en dominio público es el objetivo.
