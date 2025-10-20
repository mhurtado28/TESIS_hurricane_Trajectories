# 📚 Instrucciones para el Jupyter Book de Trayectorias de Huracanes

## ✅ Estado Actual
Tu proyecto de Jupyter Book está **completamente configurado y funcionando**. 

## 🚀 Cómo usar el libro

### 1. Ver el libro localmente
El servidor ya está ejecutándose. Puedes acceder al libro en:
- **URL local**: http://localhost:8000
- **Archivo directo**: `file:///Users/mauriciohurtado/jbook_trayectorias/_build/html/index.html`

### 2. Comandos principales

```bash
# Construir el libro (cuando hagas cambios)
jupyter-book build .

# Servir localmente
jupyter-book serve .

# Limpiar archivos de construcción
jupyter-book clean .
```

## 📁 Estructura del proyecto

```
jbook_trayectorias/
├── trayectorias_Models_MHurtado.ipynb  # 📓 Notebook principal
├── _config.yml                         # ⚙️ Configuración del libro
├── _toc.yml                           # 📑 Tabla de contenidos
├── README.md                          # 📖 Documentación
├── _build/html/                       # 🌐 Archivos HTML generados
└── jupyter_execute/                   # 🖼️ Figuras y archivos ejecutados
```

## 🎯 Características implementadas

- ✅ **Tema moderno**: Sphinx Book Theme con navegación limpia
- ✅ **Navegación**: Tabla de contenidos automática
- ✅ **Imágenes**: Todas las figuras del notebook están incluidas
- ✅ **Responsive**: Se adapta a diferentes tamaños de pantalla
- ✅ **Búsqueda**: Funcionalidad de búsqueda integrada
- ✅ **Enlaces**: Botones para editar en GitHub (configurados)

## 🔧 Personalización adicional

### Cambiar el tema
Edita `_config.yml` y modifica:
```yaml
html:
  theme:
    name: sphinx_book_theme  # Cambiar por otro tema
```

### Agregar más contenido
1. Crea nuevos notebooks `.ipynb`
2. Agrégalos a `_toc.yml`:
```yaml
format: jb-book
root: trayectorias_Models_MHurtado.ipynb
title: "Trayectorias de Huracanes"

parts:
- caption: "Nueva sección"
  chapters:
  - file: nuevo_notebook.ipynb
    title: "Nuevo Capítulo"
```

### Ejecutar notebooks automáticamente
Cambia en `_config.yml`:
```yaml
execute:
  execute_notebooks: "auto"  # En lugar de "off"
```

## 🌐 Publicación en GitHub Pages

Para publicar en GitHub Pages:

1. **Sube el código a GitHub**
2. **Habilita GitHub Pages** en Settings > Pages
3. **Configura la fuente** como "GitHub Actions"
4. **Crea `.github/workflows/deploy.yml`**:

```yaml
name: Deploy Jupyter Book

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      - name: Setup Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.x'
      - name: Install dependencies
        run: |
          pip install -U jupyter-book
          pip install sphinx-book-theme
      - name: Build book
        run: jupyter-book build .
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v2
        with:
          path: ./_build/html

  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v2
```

## 🎉 ¡Listo!

Tu Jupyter Book está completamente funcional. Puedes:
- ✅ Ver el libro en http://localhost:8000
- ✅ Editar el notebook principal
- ✅ Reconstruir con `jupyter-book build .`
- ✅ Publicar en GitHub Pages

¡Disfruta tu libro sobre trayectorias de huracanes! 🌪️📚
