# 🚀 Instrucciones para completar la configuración en GitHub

## ✅ Estado actual
- ✅ Código subido a GitHub: https://github.com/mhurtado28/TESIS_hurricane_Trajectories
- ✅ Repositorio conectado y sincronizado
- ⏳ Falta: Configurar GitHub Pages y workflow

## 📋 Pasos finales (hacer en GitHub web):

### 1. Crear el workflow de GitHub Actions
1. Ve a tu repositorio: https://github.com/mhurtado28/TESIS_hurricane_Trajectories
2. Click en "Actions" (pestaña superior)
3. Click en "set up a workflow yourself"
4. Borra el contenido existente y pega este código:

```yaml
name: Deploy Jupyter Book to GitHub Pages

on:
  push:
    branches: [ main, master ]
  pull_request:
    branches: [ main, master ]

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
          python-version: '3.11'
          
      - name: Install dependencies
        run: |
          pip install -U jupyter-book
          pip install sphinx-book-theme
          pip install myst-nb
          
      - name: Build book
        run: jupyter-book build .
        
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
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
        uses: actions/deploy-pages@v4
```

5. Click en "Start commit"
6. Escribe: "Add GitHub Pages workflow"
7. Click "Commit new file"

### 2. Habilitar GitHub Pages
1. Ve a tu repositorio → **Settings** (pestaña superior)
2. Scroll hacia abajo → **Pages** (sidebar izquierdo)
3. En "Source" selecciona **"GitHub Actions"**
4. ¡Listo!

### 3. Verificar publicación
1. Ve a la pestaña **"Actions"** en tu repositorio
2. Deberías ver el workflow ejecutándose
3. Una vez completado (5-10 minutos), tu libro estará en:
   **`https://mhurtado28.github.io/TESIS_hurricane_Trajectories/`**

## 🎉 ¡Listo!
Una vez completados estos pasos, tu libro se publicará automáticamente cada vez que hagas push al repositorio.

## 🔄 Para futuras actualizaciones:
```bash
git add .
git commit -m "Descripción de cambios"
git push origin main
```
