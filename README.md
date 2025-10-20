# Trayectorias de Huracanes

Jupyter Book sobre análisis de trayectorias de huracanes usando machine learning, con enfoque en aquellos que amenacen las Islas de San Andrés y Providencia, Caribe colombiano.

## 📖 Ver el libro en línea

El libro está disponible en: [https://mhurtado28.github.io/TESIS_hurricane_Trajectories/](https://mhurtado28.github.io/TESIS_hurricane_Trajectories/)

## 🚀 Publicación en GitHub Pages

Este libro se publica automáticamente en GitHub Pages cada vez que haces push a la rama principal.

### Configuración inicial

1. **Sube el proyecto a GitHub**:
   ```bash
   git init
   git add .
   git commit -m "Initial commit: Jupyter Book setup"
   git branch -M main
   git remote add origin https://github.com/TU_USUARIO/TU_REPOSITORIO.git
   git push -u origin main
   ```

2. **Habilita GitHub Pages**:
   - Ve a Settings > Pages en tu repositorio
   - En "Source", selecciona "GitHub Actions"
   - El workflow ya está configurado en `.github/workflows/deploy.yml`

3. **Tu libro estará disponible en**:
   `https://TU_USUARIO.github.io/TU_REPOSITORIO/`

### Construir localmente (opcional)

```bash
# Instalar dependencias
pip install -U jupyter-book sphinx-book-theme myst-nb

# Construir el libro
jupyter-book build .

# Ver localmente
python -m http.server 8000 -d _build/html
```

## 📁 Estructura del proyecto

- `trayectorias_all.ipynb` - Notebook principal con el análisis completo
- `_config.yml` - Configuración del Jupyter Book
- `_toc.yml` - Tabla de contenidos
- `jupyter_execute/` - Archivos ejecutados y figuras generadas
- `_build/` - Archivos HTML generados

## 🎯 Objetivos

- **Objetivo General**: Predecir la trayectoria e intensidad de huracanes aplicando modelos de aprendizaje automático
- **Enfoque**: Huracanes que amenacen las Islas de San Andrés y Providencia, Caribe colombiano

## 📊 Contenido

1. **ETL**: Extracción, transformación y carga de datos
2. **EDA**: Análisis Exploratorio de Datos
3. **Modelos ML**: Implementación y evaluación de modelos de machine learning
4. **Resultados**: Análisis de resultados y conclusiones

## 👨‍💻 Autor

**Mauricio Hurtado** - Análisis de trayectorias de huracanes con machine learning
