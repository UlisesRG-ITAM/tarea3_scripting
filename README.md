# TAREA 3 - Procesamiento, Entrenamiento e Inferencia
## Alumno: Ulises Reyes García
## CU: 152113

Este repositorio contiene un flujo completo para procesar datos, entrenar un modelo de Machine Learning e inferir predicciones con datos nuevos utilizando `XGBoost`.

## 📁 **Estructura del Repositorio**

```
project
├── .gitignore
├── README.md
├── src
│   ├── __init__.py
│   ├── preprocessing.py  # Funciones para procesamiento de datos
│   ├── training.py       # Funciones para entrenar el modelo
│   ├── inference.py      # Funciones para generar predicciones
├── data
│   ├── raw.csv          # Datos crudos
│   ├── prep.csv         # Datos preprocesados* (se debe de ejecutar código)
│   ├── inference.csv    # Datos de inferencia
│   ├── predictions.csv  # Predicciones generadas* (se debe de ejecutar código)
│   ├── trained_columns.json # Columnas usadas en el entrenamiento* (se debe de ejecutar código)
├── prep.py             # Script de preprocesamiento
├── train.py            # Script de entrenamiento del modelo
├── inference.py        # Script de inferencia
└── model.joblib        # Modelo entrenado* (se debe de ejecutar código)
```

## 📜 **Explicación de Scripts y Módulos**

### **Scripts en la raíz del repositorio:**
- `prep.py`: Ejecuta el preprocesamiento de datos.
- `train.py`: Entrena el modelo XGBoost y guarda las columnas utilizadas en el entrenamiento.
- `inference.py`: Realiza inferencia con nuevos datos usando el modelo entrenado.

### **Módulos en `src/`:**
- `preprocessing.py`: Contiene funciones para la limpieza de datos, imputación de valores nulos, transformación y selección de características.
- `training.py`: Incluye funciones para entrenar un modelo XGBoost, realizar optimización de hiperparámetros y guardar el modelo.
- `inference.py`: Proporciona funciones para cargar un modelo, preparar datos de inferencia y generar predicciones.

---

## 🚀 **Ejecución del Flujo Completo**

### **1️⃣ Preprocesamiento de Datos**
```bash
python prep.py --input data/raw.csv --output data/prep.csv --target SalePrice
```
✅ **Salida esperada:** `data/prep.csv` generado.

### **2️⃣ Entrenamiento del Modelo**
```bash
python train.py --input data/prep.csv --output_model model.joblib --output_columns data/trained_columns.json --target SalePrice
```
✅ **Salida esperada:** `model.joblib` y `data/trained_columns.json` generados.

### **3️⃣ Generación de Predicciones**
```bash
python inference.py --input data/inference.csv --model model.joblib --columns data/trained_columns.json --output data/predictions.csv
```
✅ **Salida esperada:** `data/predictions.csv` generado.

---

## 🛠 **Herramientas Utilizadas**
- `pandas`, `numpy` → Manipulación de datos
- `scikit-learn` → Preprocesamiento y métricas
- `xgboost` → Algoritmo de aprendizaje
- `joblib` → Guardado de modelos
- `loguru` → Manejo de logs
- `argparse` → Parámetros en CLI
- `black`, `flake8`, `pylint` → Estilo y calidad de código

```
pandas==1.5.3
numpy==1.23.5
scikit-learn==1.2.2
xgboost==1.7.3
joblib==1.2.0
loguru==0.6.0
argparse==1.4.0
black==22.3.0
flake8==5.0.4
pylint==2.15.5
```

---

## 📌 **Notas Importantes**
✅ Asegurar que los archivos de datos (`raw.csv`, `inference.csv`) estén en la carpeta `data/` antes de ejecutar los scripts.
✅ `trained_columns.json` debe existir para que la inferencia funcione correctamente.
✅ El código está optimizado para ser modular y reutilizable en producción.

---

## 📬 **Contacto y Contribuciones**
Si tienes mejoras o encuentras errores, por favor crea un **issue** o un **pull request** en este repositorio.
