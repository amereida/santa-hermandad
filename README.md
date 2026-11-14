# Santa Hermandad

Skin MediaWiki para la wiki [Amereida](http://amereida.cl), construido sobre `SkinMustache` + `skin.json`. Fork de [Stella Nova](https://github.com/hspencer/stella-nova).

Mobile-first, CSS moderno (Grid/Flexbox, light/dark), WCAG 2.1 AA, compatible con Semantic MediaWiki.

## Instalación

```php
wfLoadSkin( 'Santa Hermandad' );
$wgDefaultSkin = 'santa-hermandad';
```

Probar sin cambiar el default: `?useskin=santa-hermandad`.

La carpeta puede llamarse `Santa Hermandad`, `santa-hermandad` o ser un symlink — las URLs de assets se calculan de la carpeta real.

## Logo

El skin incrusta el SVG **inline** (no como `<img>`), así se tematiza claro/oscuro con `currentColor`.

```php
$wgSanta HermandadIsotypePath = '/ruta/absoluta/mi-logo.svg';       // wordmark
$wgSanta HermandadIconPath    = '/ruta/absoluta/mi-icono.svg';      // glifo compacto
```

Sin config usa los bundles en `resources/` (`amereida-cruces.svg`, `casiopea-icon.svg`). El SVG debe ser monocromo (`fill="currentColor"`), fondo transparente, texto como `<path>`. Ver `docs/DISENO.md` para las reglas completas.

## Chrome editable: Aviso y Pie

Dos slots se editan como páginas wiki, no en código:

| Slot | Página | Efecto |
|------|--------|--------|
| Aviso (cabecera) | `Santa Hermandad:Aviso` | Banner en todas las páginas |
| Pie institucional | `Santa Hermandad:Pie` | Footer del sitio |

Si la página está vacía o no existe, el slot no se muestra. Para retirar un aviso, **vacía la página** (no la borres).

### Namespace protegido (recomendado)

```php
define( 'NS_STELLAMEREIDA', 3000 );
define( 'NS_STELLAMEREIDA_TALK', 3001 );
$wgExtraNamespaces[NS_STELLAMEREIDA]      = 'Santa Hermandad';
$wgExtraNamespaces[NS_STELLAMEREIDA_TALK] = 'Santa Hermandad_discusión';
$wgNamespaceProtection[NS_STELLAMEREIDA]  = [ 'editinterface' ];
```

Sin el namespace, el skin cae a páginas del espacio principal con título literal `Santa Hermandad:Aviso` (funciona, pero sin protección de escritura).

## Documentación

- [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md) — principios y doctrina
- [`docs/DEVELOPMENT.md`](docs/DEVELOPMENT.md) — roadmap y workflow
- [`docs/LAYOUTS.md`](docs/LAYOUTS.md) — esquemas de layout
- [`docs/DISENO.md`](docs/DISENO.md) — guía para diseño visual
- [`docs/EXTENSIONES.md`](docs/EXTENSIONES.md) — compatibilidad con extensiones
- [`docs/WIKITEXTO.md`](docs/WIKITEXTO.md) — clases CSS y palabras mágicas para editores
- [`specs/santa-hermandad.allium`](specs/santa-hermandad.allium) — spec de comportamiento

## Licencia

**Artistic License 2.0** — ver [`COPYING`](COPYING).

Copyright © 2026 Herbert Spencer González · .:TIG:. · e[ad] PUCV · Corporación Cultural Amereida.

Dos archivos en `resources/skinStyles/` conservan licencia GPL-2.0-or-later.
