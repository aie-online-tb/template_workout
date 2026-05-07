# template_workout

Plantilla HTML con **botones dinámicos** para:

- GitHub Codespaces (abre el repo)
- Google Colab (abre un `.ipynb` dentro del repo)

## Query params (opción A)

- **`repo`** (obligatorio): `owner/repo`
- **`ref`** (opcional): rama/tag/sha. Default: `main`
- **`path`** (opcional): ruta al `.ipynb` dentro del repo (si no está, Colab se deshabilita)
- **`title`**, **`subtitle`**, **`hint`** (opcionales): textos del panel

## Ejemplos (Live Server)

Con Live Server, tu URL base es:

- `http://127.0.0.1:5500/index.html`

Prueba estos ejemplos:

### 7_Funciones (Colab + Codespaces)

`http://127.0.0.1:5500/index.html?repo=aie-online-tb/aie-prework&ref=main&path=notebooks/7_Funciones.ipynb&title=Ejercicio%207&subtitle=Funciones`

### 8_Diccionarios (Colab + Codespaces)

`http://127.0.0.1:5500/index.html?repo=aie-online-tb/aie-prework&ref=main&path=notebooks/8_Diccionarios.ipynb&title=Ejercicio%208&subtitle=Diccionarios`

### Solo Codespaces (sin `path`)

`http://127.0.0.1:5500/index.html?repo=aie-online-tb/aie-prework&ref=main&title=Repo%20en%20Codespaces&hint=Colab%20requiere%20path%20al%20ipynb`