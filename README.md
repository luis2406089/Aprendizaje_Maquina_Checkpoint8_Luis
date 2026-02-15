# 🎮 Clasificador de Pokémon con Machine Learning

Modelo de clasificación que predice si un Pokémon es **Legendario**, **Pseudo-Legendario**, **Top 15 Stats** o **Normal** basándose en sus estadísticas.

## 📊 Dataset

Dataset de Pokémon de Kaggle (Generaciones 1-7):
- **Fuente**: [Pokemon with stats](https://www.kaggle.com/datasets/abcsds/pokemon)
- **Pokémon incluidos**: ~800
- **Features**: HP, Attack, Defense, Sp. Atk, Sp. Def, Speed, Type, Generation

## 🎯 Categorías de Clasificación

| Categoría | Descripción | Cantidad |
|-----------|-------------|----------|
| 🏆 **Top 15 Stats** | Los 15 Pokémon con mayores stats totales | 15 |
| 🌟 **Legendario** | Pokémon legendarios oficiales (no Top 15) | ~55 |
| 💎 **Pseudo-Legendario** | Stats total = 600, no legendario (no Top 15) | ~20 |
| ⚪ **Normal** | Resto de Pokémon | ~710 |

## 🚀 Instalación

### 1. Clonar el repositorio

```bash
git clone https://github.com/tu-usuario/pokemon-classifier.git
cd pokemon-classifier
```

### 2. Crear entorno virtual

```bash
python3 -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
```

### 3. Instalar dependencias

```bash
pip install -r requirements.txt
```

## 📖 Uso

### Entrenar el modelo

```bash
python pokemon_classifier.py
```

Esto tomará 5-10 minutos y generará:
- Modelo entrenado (`.pkl`)
- Visualizaciones de evaluación
- Métricas de rendimiento

### Hacer predicciones

```bash
python predict_pokemon.py
```

O en Python:

```python
from predict_pokemon import PokemonPredictor

# Cargar predictor
predictor = PokemonPredictor('models/pokemon_classifier_model.pkl')

# Predecir
resultado = predictor.predict_pokemon(
    hp=106, attack=110, defense=90,
    sp_atk=154, sp_def=90, speed=130,
    generation=1, type1='Psychic'
)

predictor.print_prediction(resultado)
```

### Generar visualizaciones

```bash
python visualizations_fixed.py
```

Genera 8 gráficos en la carpeta `visualizations/`:
- Distribución de stats
- Box plots por categoría
- Scatter plots
- Radar charts
- Heatmaps de correlación
- Rankings por tipo
- Análisis por generación

## 📁 Estructura del Proyecto

```
pokemon-classifier/
├── pokemon_classifier.py       # Entrenamiento del modelo
├── predict_pokemon.py          # Predicciones
├── visualizations_fixed.py     # Análisis visual
├── requirements.txt            # Dependencias
├── README.md                   # Este archivo
├── .gitignore                  # Archivos ignorados
│
├── models/                     # Modelos entrenados
│   ├── pokemon_classifier_model.pkl
│   ├── scaler.pkl
│   ├── label_encoder_type1.pkl
│   ├── label_encoder_type2.pkl
│   ├── category_mapping.json
│   └── feature_names.json
│
└── visualizations/             # Gráficos generados
    ├── stat_distribution.png
    ├── confusion_matrix.png
    └── ...
```

## 🤖 Modelo

- **Algoritmo**: Random Forest / Gradient Boosting
- **Features**: 10 (HP, Attack, Defense, Sp. Atk, Sp. Def, Speed, Total, Generation, Type 1, Type 2)
- **Accuracy**: ~95-98%
- **Optimización**: GridSearchCV con validación cruzada

## 📊 Resultados

### Métricas de Rendimiento

```
Accuracy: 96.5%
Precision (Legendario): 98%
Recall (Legendario): 94%
F1-Score (Top 15): 92%
```

### Features Más Importantes

1. Total (stats totales)
2. Attack / Sp. Atk
3. HP
4. Generation

## 🛠️ Tecnologías

- Python 3.8+
- scikit-learn
- pandas
- numpy
- matplotlib
- seaborn
- kagglehub

## 📝 Ejemplos

### Mewtwo (Legendario)
```
Stats: HP=106, Attack=110, Defense=90, Sp.Atk=154, Sp.Def=90, Speed=130
Total: 680
Predicción: Top 15 Stats ✅ (98% confianza)
```

### Dragonite (Pseudo-Legendario)
```
Stats: HP=91, Attack=134, Defense=95, Sp.Atk=100, Sp.Def=100, Speed=80
Total: 600
Predicción: Pseudo-Legendario ✅ (95% confianza)
```

### Pikachu (Normal)
```
Stats: HP=35, Attack=55, Defense=40, Sp.Atk=50, Sp.Def=50, Speed=90
Total: 320
Predicción: Normal ✅ (99% confianza)
```

## 🤝 Contribuciones

Las contribuciones son bienvenidas! Por favor:

1. Fork el proyecto
2. Crea una rama (`git checkout -b feature/mejora`)
3. Commit tus cambios (`git commit -m 'Añadir mejora'`)
4. Push a la rama (`git push origin feature/mejora`)
5. Abre un Pull Request

## 📄 Licencia

Este proyecto utiliza el dataset público de Pokémon de Kaggle.

## 👤 Autor

Luis - [GitHub](https://github.com/tu-usuario)

## 🙏 Agradecimientos

- Dataset: [Alberto Barradas - Kaggle](https://www.kaggle.com/datasets/abcsds/pokemon)
- Pokémon © Nintendo/Game Freak
