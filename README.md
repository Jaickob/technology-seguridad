# Seguridad de la Información · Technology Solutions
 
Sitio del área de Seguridad de la Información, listo para desplegar en GitHub Pages.
 
## Archivos
 
| Archivo | Qué es |
|---|---|
| `index.html` | Página principal (home del área) |
| `novedades.html` | Listado de todas las noticias, con filtro por categoría |
| `articulo.html` | Plantilla de lectura de un artículo (carga el contenido según la URL) |
| `noticias.json` | **El único archivo que editas** para publicar y redactar noticias |
| `README.md` | Este documento |
 
## Cómo funciona
 
- `index.html` muestra las noticias más recientes (la primera como destacada).
- `novedades.html` muestra todas, con filtros por categoría.
- Al hacer clic en una noticia se abre `articulo.html?id=<id-de-la-noticia>`, que carga ese artículo desde `noticias.json`.
Una sola plantilla (`articulo.html`) sirve para todos los artículos. No necesitas crear un HTML por noticia.
 
## Cómo publicar una noticia nueva
 
Edita `noticias.json` y agrega un bloque al inicio de la lista (la primera noticia se muestra como destacada):
 
```json
{
  "id": "identificador-unico-sin-espacios",
  "categoria": "Aviso",
  "titulo": "Título de la novedad",
  "resumen": "Una o dos frases para las tarjetas.",
  "fecha": "20 MAY 2026",
  "autor": "Equipo de Seguridad de la Información",
  "contenido": [
    { "tipo": "parrafo", "texto": "Primer párrafo del artículo." },
    { "tipo": "subtitulo", "texto": "Un subtítulo" },
    { "tipo": "parrafo", "texto": "Más texto." },
    { "tipo": "lista", "items": ["Punto uno", "Punto dos", "Punto tres"] },
    { "tipo": "cita", "texto": "Una frase destacada." }
  ]
}
```
 
### Campos
 
- **id**: identificador único, sin espacios ni acentos (ej. `actualizacion-mfa-2026`). Es lo que va en la URL.
- **categoria**: `Destacado`, `Aviso`, `Boletín`, `Certificación`, `Buenas prácticas` (tienen ícono propio). Otras categorías usan un ícono genérico.
- **titulo / resumen / fecha / autor**: texto simple.
- **contenido**: lista de bloques del artículo. Tipos disponibles:
  - `parrafo` → texto normal (campo `texto`)
  - `subtitulo` → título de sección (campo `texto`)
  - `lista` → viñetas (campo `items`, un arreglo de textos)
  - `cita` → frase destacada (campo `texto`)
Guarda, haz commit a GitHub y el sitio se actualiza solo.
 
> Si `noticias.json` no se puede cargar (por ejemplo abriendo el HTML con doble clic), `index.html` y `novedades.html` muestran noticias de respaldo. Para ver el contenido completo de los artículos hace falta servir los archivos (ver abajo).
 
## Probar en tu PC
 
Los navegadores bloquean `fetch` de archivos locales, así que ábrelo con un servidor local:
 
```bash
python -m http.server
```
 
Luego entra a `http://localhost:8000`.
 
## Desplegar en GitHub Pages
 
1. Sube todos los archivos a un repositorio.
2. **Settings → Pages** → rama `main`, carpeta raíz (`/root`). Guarda.
3. En 1–2 minutos queda publicado en `https://<usuario>.github.io/<repo>/`.
## Integración con technologylatam.com
 
Los enlaces del menú/footer a `index.php`, `soluciones.php`, etc. y los PDFs de política apuntan a rutas del sitio actual. Ajústalas si la estructura de carpetas cambia al integrar.
 
## Opcional: noticias desde Google Sheets
 
Si más adelante prefieres editar desde una planilla en vez de JSON, se puede publicar una Google Sheet como JSON y cambiar la URL del `fetch()`. Avísame y lo configuramos.
 
