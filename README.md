# template_workout

Plantilla HTML con **2 botones (badges) dinámicos** para:

- GitHub Codespaces (abre el repo)
- Google Colab (abre un `.ipynb` dentro del repo)

La idea es publicar este repo en **GitHub Pages** y compartir links con **query params** para que el mismo `index.html` sirva para todos los ejercicios.

## Parámetros (query params)

- **`repo`**: `owner/repo` (si no lo pasas, se usan los links por defecto del HTML)
- **`ref`**: rama/tag/sha (opcional, default `main`)
- **`path`**: ruta al `.ipynb` dentro del repo (opcional; si no está, Colab se desactiva cuando `repo` sí está)
- **`mode`**: `colab` o `codespaces` (opcional)
  - `mode=colab` → **se oculta Codespaces**
  - `mode=codespaces` → **se oculta Colab**
  - sin `mode` → se ven ambos (si falta `path`, Colab queda desactivado)

**Importante:** en la barra del navegador deben aparecer caracteres **`=`** y **`&`** entre parámetros, por ejemplo  
`...?mode=codespaces&repo=owner/repo&ref=main`  
Si pegas algo como `?mode%3Dcodespaces%26repo%3D...`, muchas veces viene de una herramienta que **codifica dos veces** la URL (el launcher ahora intenta corregirlo, pero mejor usar la forma no codificada).

## Ejemplos (Live Server)

Con Live Server, tu URL base es:

- `http://127.0.0.1:5500/index.html`

Prueba estos ejemplos:

### Solo Colab (se oculta Codespaces)

- `http://127.0.0.1:5500/index.html?mode=colab&repo=aie-online-tb/aie-prework&ref=main&path=notebooks/7_Funciones.ipynb`
- `http://127.0.0.1:5500/index.html?mode=colab&repo=aie-online-tb/aie-prework&ref=main&path=notebooks/8_Diccionarios.ipynb`

Ejemplo “solo Colab” para GitHub Pages (cambia ORG/REPO):

- `https://NOMBRE_ORG.github.io/NOMBRE_REPO/index.html?mode=colab&repo=aie-online-tb/aie-prework&ref=main&path=notebooks/8_Diccionarios.ipynb`

### Solo Codespaces (se oculta Colab)

- `http://127.0.0.1:5500/index.html?mode=codespaces&repo=aie-online-tb/aie-prework&ref=main`

### Ambos (sin `mode`)

- `http://127.0.0.1:5500/index.html?repo=aie-online-tb/aie-prework&ref=main&path=notebooks/7_Funciones.ipynb`

## Despliegue en GitHub Pages (organización)

1. Crea un repo en la **organización** y sube `index.html` (y opcionalmente `style.css`/`README.md`).
2. En el repo: **Settings → Pages**
   - **Source**: “Deploy from a branch”
   - **Branch**: `main`
   - **Folder**: `/ (root)`
3. La URL quedará como:
   - `https://NOMBRE_ORG.github.io/NOMBRE_REPO/index.html`

Ejemplo ya desplegado (cambia ORG/REPO):

- `https://NOMBRE_ORG.github.io/NOMBRE_REPO/index.html?mode=colab&repo=aie-online-tb/aie-prework&ref=main&path=notebooks/8_Diccionarios.ipynb`