# Visualización Analítica con Altair

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Quarto](https://img.shields.io/badge/Built_with-Quarto-2196F3)](https://quarto.org/)

Sitio web interactivo de visualización de datos desarrollado como parte de la Maestría en Ciencia de Datos. Este proyecto utiliza Quarto, Python y la biblioteca Altair para crear visualizaciones interactivas que transforman datos complejos en historias visuales comprensibles.

## 📊 Características

- **Visualizaciones Interactivas**: Gráficos generados con Altair y Vega-Lite
- **Análisis Exploratorio**: EDA completo de datasets clásicos de ciencia de datos
- **Código Reproducible**: Notebooks Quarto con código Python listo para ejecutar
- **Sitio Web Estático**: Generado automáticamente por Quarto
- **Múltiples Tipos de Análisis**: Univariate, bivariate, series temporales, EDA, visualización de texto y geográfica

## 🚀 Contenido del Proyecto

### Secciones Principales

1. **Visualización** - Gráficos interactivos del dataset Cars (`viz.qmd`)
2. **Análisis Univariado** - Distribuciones y análisis de una variable (`univariate.qmd`)
3. **Análisis Bivariado** - Relaciones entre dos variables (`bivariate.qmd`)
4. **Series de Tiempo** - Análisis temporal de datos (`series.qmd`)
5. **EDA** - Análisis Exploratorio de Datos completo (`eda.qmd`)
6. **Visualización de Texto** - Procesamiento y análisis de datos textuales (`text.qmd`)
7. **Visualización Geográfica** - Mapas y datos geoespaciales (`geo.qmd`)

### Tecnologías Utilizadas

- **Python 3** - Lenguaje principal de análisis
- **Altair** - Visualizaciones declarativas basadas en Vega-Lite
- **Pandas** - Manipulación y análisis de datos
- **Quarto** - Sistema de publicación científica y técnica
- **Vega Datasets** - Conjuntos de datos predefinidos para análisis
- **NLTK** - Procesamiento de lenguaje natural (para análisis de texto)
- **GeoPandas** - Datos geoespaciales (para visualización geográfica)

## 📦 Instalación y Uso

### Prerrequisitos

```bash
# Instalar Python 3.8 o superior
# Instalar pip o conda

# Instalar Quarto (si se desea regenerar el sitio)
# Descargar desde: https://quarto.org/docs/get-started/
```

### Configuración del Entorno

```bash
# Clonar el repositorio
git clone https://github.com/yourusername/viz-altair.git
cd viz-altair

# Crear entorno virtual (opcional pero recomendado)
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate

# Instalar dependencias
pip install -r requirements.txt  # Si existe requirements.txt
# O instalar manualmente:
pip install altair pandas vega_datasets nltk geopandas
```

### Ejecutar el Proyecto

#### Opción 1: Ver el sitio web generado

El sitio web ya está generado en la carpeta `docs/`. Simplemente abre `docs/index.html` en tu navegador.

#### Opción 2: Regenerar el sitio con Quarto

```bash
# Instalar Quarto primero
# Generar el sitio web
quarto render

# Previsualizar en navegador
quarto preview
```

#### Opción 3: Ejecutar notebooks individuales

Cada archivo `.qmd` es un notebook Quarto que puede ejecutarse individualmente:

```bash
quarto render nombre-del-archivo.qmd
```

## 📁 Estructura del Proyecto

```
viz-altair/
├── *.qmd                      # Notebooks Quarto con análisis
├── docs/                      # Sitio web generado
│   ├── *.html                 # Páginas HTML generadas
│   └── site_libs/             # Librerías y estilos
├── _quarto.yml               # Configuración de Quarto
├── .gitignore                # Archivos ignorados por Git
├── README.md                 # Este archivo
└── LICENSE                   # Licencia MIT
```

### Archivos Principales

- `_quarto.yml` - Configuración del sitio web Quarto
- `index.qmd` - Página principal del sitio
- `about.qmd` - Información sobre el proyecto
- `viz.qmd` - Visualizaciones principales con dataset Cars
- `univariate.qmd`, `bivariate.qmd` - Análisis estadístico
- `series.qmd` - Análisis de series temporales
- `eda.qmd` - Análisis exploratorio de datos
- `text.qmd` - Visualización de datos textuales
- `geo.qmd` - Visualización geográfica

## 🔧 Desarrollo

### Regenerar el Sitio

```bash
# Renderizar todos los notebooks
quarto render

# Renderizar solo un notebook específico
quarto render viz.qmd

# Crear PDF de un notebook (si está configurado)
quarto render notebook.qmd --to pdf
```

### Estructura de los Notebooks

Cada notebook Quarto (`.qmd`) contiene:

- **Código Python ejecutable**
- **Visualizaciones Altair interactivas**
- **Explicaciones en Markdown**
- **Salidas integradas**

### Personalización

1. **Modificar configuraciones**: Editar `_quarto.yml`
2. **Agregar nuevos datasets**: Importar desde `vega_datasets` o URLs
3. **Crear nuevas visualizaciones**: Usar la sintaxis Altair
4. **Cambiar tema**: Modificar `theme` en `_quarto.yml`

## 📈 Ejemplos de Código

```python
# Cargar dataset
from vega_datasets import data
import altair as alt

cars = data.cars()

# Crear gráfico interactivo
scatter = alt.Chart(cars).mark_circle(size=60, opacity=0.7).encode(
    x="Horsepower:Q",
    y="Miles_per_Gallon:Q",
    color="Origin:N",
    tooltip=["Name:N", "Horsepower:Q", "Miles_per_Gallon:Q"]
).properties(width=600, height=400).interactive()

scatter
```

## 🤝 Contribución

Las contribuciones son bienvenidas. Por favor:

1. Fork el repositorio
2. Crear una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abrir un Pull Request

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo [LICENSE](LICENSE) para más detalles.

## 👤 Autor

**FAGR**

> "Un buen gráfico vale más que mil filas de datos."

**Enlaces útiles**:

- [Documentación de Quarto](https://quarto.org/)
- [Documentación de Altair](https://altair-viz.github.io/)
- [Vega Datasets](https://github.com/vega/vega-datasets)
- [Repositorio del Curso](https://github.com/erickedu85/dataset)
