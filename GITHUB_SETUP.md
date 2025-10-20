# Guía de publicación en GitHub Pages

## 🚀 Pasos para conectar con GitHub

### 1. Crear repositorio en GitHub
1. Ve a https://github.com/new
2. Nombre del repositorio: `TESIS_hurricane_Trajectories` (o el que prefieras)
3. Descripción: "Análisis de trayectorias de huracanes usando machine learning"
4. Marca como público
5. NO inicialices con README (ya tienes uno)

### 2. Conectar repositorio local
```bash
# Ya tienes el repositorio inicializado, ahora conecta con GitHub:
git remote add origin https://github.com/mhurtado28/TESIS_hurricane_Trajectories.git
git branch -M main
git push -u origin main
```

### 3. Configurar GitHub Pages
1. Ve a tu repositorio en GitHub
2. Click en "Settings" (pestaña superior)
3. Scroll hacia abajo hasta "Pages" (sidebar izquierdo)
4. En "Source", selecciona "GitHub Actions"
5. El workflow ya está configurado en `.github/workflows/deploy.yml`

### 4. Verificar publicación
- Ve a la pestaña "Actions" en tu repositorio
- Deberías ver el workflow ejecutándose
- Una vez completado, tu libro estará en:
  `https://mhurtado28.github.io/TESIS_hurricane_Trajectories/`

## 🔄 Actualizaciones futuras

Cada vez que hagas cambios y hagas push:
```bash
git add .
git commit -m "Descripción de los cambios"
git push
```

El libro se actualizará automáticamente en GitHub Pages.

## 📁 Archivos importantes

- `.github/workflows/deploy.yml` - Workflow de GitHub Actions
- `_config.yml` - Configuración del Jupyter Book
- `_toc.yml` - Tabla de contenidos
- `trayectorias_Models_MHurtado.ipynb` - Notebook principal

## ⚠️ Notas importantes

- El repositorio debe ser público para GitHub Pages gratuito
- Los cambios pueden tardar unos minutos en aparecer
- Revisa la pestaña "Actions" si hay problemas
