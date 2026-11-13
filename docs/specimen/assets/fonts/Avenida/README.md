# Avenida — webfonts

24 fuentes estáticas WOFF2: Avenida y Avenida Condensed, cada una con seis pesos en normal e italic. Se conserva el repertorio completo de cada OTF, sus contornos, métricas y tablas de funciones OpenType; no se ha aplicado subset.

## Uso

Copia esta carpeta conservando las rutas relativas y enlaza el CSS:

```html
<link rel="stylesheet" href="Avenida-webfonts/avenida.css">
```

```css
body { font-family: 'Avenida', sans-serif; font-weight: 400; }
h1 { font-family: 'Avenida Condensed', sans-serif; font-weight: 700; }
em { font-style: italic; }
```

Pesos: Ultra Light 275, Regular 400, Medium 500, Demi 600, Bold 700, Heavy 900. Los dos anchos se seleccionan mediante nombres de familia diferentes.

Abre index.html para ver todas las variantes. Para servir la muestra localmente desde esta carpeta: `python3 -m http.server 8000` y visita http://localhost:8000.

## Conversión y verificación

Conversión realizada con fontTools 4.61.1 y Brotli. Los nombres internos de familia, estilo y PostScript se actualizaron a Avenida / Avenida Condensed. Se conservaron los avisos originales de autoría, copyright y marca de las fuentes de origen.

Se reabrieron los 24 WOFF2 y se comprobaron repertorio, orden de glifos, todas las operaciones y coordenadas de los contornos, métricas horizontales, OS/2 y las tablas GSUB, GPOS y GDEF presentes. Se verificó con SHA-256 que los originales no cambiaron. El manifiesto identifica cada origen y archivo resultante.

No se realizó una prueba visual en navegador ni se verificaron los términos de la licencia institucional para publicación web. Esta entrega contiene fuentes estáticas; la futura fuente variable requiere el trabajo descrito en variable-work.
