# Santa Hermandad — espécimen gráfico

Skin para MediaWiki diseñado para la **Corporación Cultural Amereida** ([amereida.cl](http://amereida.cl)).
Hermano de [Stella Nova](https://github.com/hspencer/stella-nova), del cual toma su fundamento
tipográfico y estructural.

Este mini-sitio muestra las variables de diseño, los componentes y diagramaciones
simuladas del skin para iteración con el taller de diseño.

**Ver online →** https://amereida.github.io/santa-hermandad/specimen/


## Páginas

| Archivo | Contenido |
|---------|-----------|
| `index.html` | Fundamentos: paleta, tipografía, escala, sombras |
| `components.html` | Componentes: botones, inputs, toolbar, menús |
| `aplicados.html` | Página tipo con el marco completo del skin |
| `aplicados-tipografia.html` | Tipografía en contexto: cuerpo, cabeceras, verso, cita |
| `aplicados-grilla.html` | Grilla baseline y ritmo vertical |
| `aplicados-tablas.html` | Tablas de datos y wikitables |
| `aplicados-imagenes.html` | Imágenes, galerías y thumbnails |
| `aplicados-diagramaciones.html` | Layouts de contenido y columnas |

No necesita servidor. Las fuentes y CSS van inlinados en `assets/`.


## Tokens de color

Los colores se organizan en tres capas. Solo la **capa semántica** se usa en
componentes y plantillas wiki; las primitivas son vocabulario interno.

### Capa 1 — Primitivas

Nombradas por matiz, no por uso. Stops numerados por luminancia.

| Primitiva | Carácter |
|-----------|----------|
| `--sh-papel-*` | Naranja luminoso diluido (la hoja, los pliegues) |
| `--sh-tinta-*` | Verde petróleo profundo (superficies nocturnas) |
| `--sh-morado-*` | Violeta apenas (tinta diurna) |
| `--sh-rosa-*` | Rosa pálido (redlinks, tinta nocturna) |
| `--sh-rojo-*` | Carmín (nova y enlaces claros) |
| `--sh-coral-*` | Rosa cálido (nova y enlaces oscuros) |
| `--sh-azul-*` | Único frío (enlaces nocturnos) |
| `--sh-verde-*` | Ok del taller |
| `--sh-masking-*` | Cinta amarilla del taller (avisos) |

### Capa 2 — Semántica

Cada token apunta a primitivas con `light-dark()`: el flip de tema es automático.

**Superficies** — `--sh-field` (fondo de página), `--sh-paper` (hoja),
`--sh-paper-edge` (borde), `--sh-paper-raised` (tarjetas), `--sh-sunk` (code blocks),
`--sh-edit-surface` (textarea de wikitexto).

**Texto** — `--sh-ink` (principal), `--sh-ink-soft` (secundario),
`--sh-ink-faint` (terciario/placeholder), `--sh-hairline` (filetes).

**Acento** — `--sh-nova` (único acento, usado con avaricia),
`--sh-nova-ink` (texto sobre nova), `--sh-nova-wash` (lavado suave).

**Enlaces** — `--sh-link`, `--sh-link-hover`, `--sh-link-visited`,
`--sh-link-new` (página inexistente).

**Señales** — `--sh-ok`, `--sh-warn`, `--sh-danger` + sus lavados (`*-wash`).

**Íconos** — `--sh-icon` (reposo, ~55% de tinta), `--sh-icon-active` (plena).

### Capa 3 — Componente

Derivada de la semántica:

- **3a. Controles**: `--sh-btn-*` (botones), `--sh-field-*` (inputs),
  `--sh-on-*` (checkbox/radio activos), `--sh-focus-*` (foco = nova).
- **3b. Alias Codex**: mapeo de variables WikimediaUI a tokens `--sh-*`
  para que OOUI respete el tema.


## Cómo proponer cambios

1. Abre el HTML y edita el bloque `<style id="overrides">`:
   ```css
   :root {
     --sh-nova: #c33;
     --sh-fs-display: 2.4rem;
   }
   ```
2. Recarga — los cambios se propagan.
3. Anota en `notes.md` y devuelve.


## Regenerar el espécimen

```bash
python3 scripts/build-specimen.py
```

Recompone `docs/specimen/` desde `resources/tokens.css` y `resources/santa-hermandad.css`.
`notes.md` se preserva; los `overrides` en los HTML se pierden.


## GitHub Pages

Rama `main`, carpeta `/docs`:

    https://amereida.github.io/santa-hermandad/specimen/
