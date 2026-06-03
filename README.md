# Seguridad de la Información · Technology Solutions

Página web del área de Seguridad de la Información, lista para desplegar en GitHub Pages.

## Archivos

| Archivo | Qué es |
|---|---|
| `index.html` | La página completa (estructura, estilos y lógica, todo en un archivo) |
| `noticias.json` | Las noticias del área. **Este es el único archivo que editas para publicar novedades.** |
| `README.md` | Este documento |

## Cómo publicar una noticia nueva

1. Abre `noticias.json`.
2. Agrega un bloque al inicio de la lista (la primera noticia se muestra como **destacada**):

```json
{
  "categoria": "Aviso",
  "titulo": "Título de la novedad",
  "resumen": "Una o dos frases que describen la noticia.",
  "fecha": "20 MAY 2026",
  "enlace": "https://technologylatam.com/mi-noticia.php"
}
```

3. Guarda y sube el cambio (commit) a GitHub. La página se actualiza sola.

**Categorías que ya tienen ícono:** `Destacado`, `Aviso`, `Boletín`, `Certificación`, `Buenas prácticas`. Puedes usar otras; tomarán un ícono genérico de escudo.

> Si `noticias.json` no se puede cargar (por ejemplo abriendo el archivo directamente con doble clic), la página muestra noticias de respaldo incluidas en `index.html`. Al desplegarse en un servidor o GitHub Pages, carga el JSON normalmente.

## Desplegar en GitHub Pages

1. Crea un repositorio nuevo en GitHub y sube los tres archivos.
2. Ve a **Settings → Pages**.
3. En **Source**, elige la rama `main` y carpeta `/root`. Guarda.
4. En 1–2 minutos la página queda publicada en `https://<usuario>.github.io/<repo>/`.

## Integración con technologylatam.com

Los enlaces del menú y del footer (`index.php`, `soluciones.php`, etc.) y los PDFs de política apuntan a rutas relativas del sitio actual. Cuando esta página se integre al dominio, ajusta esas rutas si la estructura de carpetas cambia.

## Opcional: noticias desde Google Sheets

Si más adelante prefieres editar las noticias desde una hoja de cálculo en lugar de un archivo JSON, se puede publicar una Google Sheet como JSON/CSV y cambiar la URL del `fetch()` en `index.html`. Avísame y lo dejamos configurado.
