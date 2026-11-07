# Portafolio Maestro · KONFÍO ZINC

Vitrina con **los 36 sitios de cliente publicados**, agrupados por tipo de producto. Es la carta de
ventas: cada tarjeta abre el sitio real del cliente.

- Página: `index.html` (autocontenida: CSS en línea, sin dependencias externas)
- Logos: `assets/logos/` (optimizados a 160 px, ~20 KB cada uno en vez de los originales de 500 KB)
- Ficha de datos: `portafolio-datos.json` (nombre, URL, categoría y logo de cada cliente)

## Cómo se regenera

La página **no se edita a mano**: se genera desde lo que ya está medido en los proyectos.

```powershell
cd C:\Users\usuario29\Documents\KONFIO_ZINC
node evidencias\KZ-PORTAFOLIO-001\generar-portafolio.mjs            # ver qué haría
node evidencias\KZ-PORTAFOLIO-001\generar-portafolio.mjs --aplicar  # escribir
node evidencias\KZ-PORTAFOLIO-001\medir-portafolio.mjs              # medir en Chromium + capturas
```

Si cambia un cliente (nuevo logo, sitio nuevo, cambio de nombre), se vuelve a ejecutar el generador:
no hay contenido escrito a mano que se pueda desincronizar.

## Categorías

| Sección | Clientes |
|---|---:|
| Menús digitales | 3 |
| Tarjetas de presentación | 25 |
| Catálogos y tiendas | 2 |
| Landing pages y sitios | 6 |

## Publicación (pendiente de un paso tuyo)

El sitio debe vivir en la **raíz de la organización**, `https://konfiozinc.github.io/`, que la sirve un
repositorio llamado **`konfiozinc.github.io`**. Ese repositorio **no existe todavía** y desde este
entorno no puedo crearlo (no hay `gh` ni acceso a la API de GitHub, solo SSH de git).

Pasos (2 minutos):

1. En GitHub: **New repository** → nombre **`konfiozinc.github.io`** → público → sin README.
2. Avisar y el resto lo hago yo con un push:

```powershell
cd C:\Users\usuario29\Documents\KONFIO_ZINC\6-LANDING-PAGES\Portafolio-Maestro
git remote add origin git@github.com:konfiozinc/konfiozinc.github.io.git
git push -u origin main
```

Alternativa mientras exista el repositorio raíz: publicarlo como una página más del sitio de la agencia
(por ejemplo `https://konfiozinc.github.io/card/`). No se hizo para no duplicar contenido: la fuente es
este directorio y el generador.

## Verificación aplicada

- Puerta de calidad de KONFÍO ZINC: **1/1 páginas OK** (título, descripción, Open Graph, favicon, `alt`).
- Medición en Chromium a 375, 768 y 1200 px: **36 tarjetas, 4 secciones, 0 desbordes, 0 imágenes rotas,
  36 enlaces únicos** (`evidencias/KZ-PORTAFOLIO-001/`).
