# Aprendizaje_Maquina_Checkpoint8_Luis
Laboratorio de modelo de entrenamiento

# Laboratorio 4: Detección de Fraude con Regresión Logística

Este repositorio contiene un notebook que implementa un modelo de regresión logística para detectar transacciones fraudulentas, utilizando el conjunto de datos Fraudulent Transactions Data disponible en Kaggle, sin embargo, el notebook incluye ya la descarga de los datos desde un bucket público de AWS. 

Deberás mostrar exploración, preprocesamiento, entrenamiento del modelo y evaluación del desempeño.

---

## **Contenido del Repositorio**

1. **`1_regresion_logistica_fraude.ipynb`:**  
   Notebook con el ciclo completo de un modelo de regresión logística:
   - Carga y exploración del conjunto de datos.
   - Preprocesamiento (normalización de características).
   - Entrenamiento del modelo.
   - Evaluación del modelo.

2. **`requirements.txt`:**  
   Archivo con las dependencias necesarias para ejecutar el notebook.

---

## **Requisitos**

Antes de ejecutar el notebook, asegúrate de tener instaladas las siguientes dependencias:
- Python 3.8 o superior
- Bibliotecas enumeradas en `requirements.txt`

---

## **Tutorial para configurar el entorno**

### 1. Crear un entorno virtual
Un entorno virtual te permite mantener aisladas las dependencias del proyecto. Sigue estos pasos:

#### En sistemas Windows:
```bash
python -m venv venv
```

#### En sistemas MacOS/Linux:
```bash
python3 -m venv venv
```

### 2. Activar el entorno virtual

#### En sistemas Windows:
```bash
venv\Scripts\activate
```

#### En sistemas MacOS/Linux:
```bash
source venv/bin/activate
```

Cuando el entorno virtual esté activado, verás un prefijo `(venv)` en tu terminal.

---

### 3. Instalar las dependencias
Este repositorio ya incluye un archivo `requirements.txt` con todas las dependencias necesarias. Una vez que el entorno virtual esté activado, instala las dependencias ejecutando:

```bash
pip install -r requirements.txt
```

Esto instalará automáticamente las librerías necesarias, como `pandas`, `scikit-learn`, `seaborn`, y otras.

---

## **Cómo usar los notebooks**

1. Asegúrate de tener el entorno virtual activado.
2. Inicia Jupyter Lab desde la terminal:
   ```bash
   jupyter lab
   ```
3. Abre el notebook `1_regresion_logistica_fraude.ipynb` y sigue las instrucciones para completar las actividades.
