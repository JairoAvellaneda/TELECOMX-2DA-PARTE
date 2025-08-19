# Telecom X - Parte 2: Predicción de Cancelación de Clientes

## Propósito del Proyecto

Este análisis tiene como objetivo principal predecir la cancelación de clientes (`Churn`) en una empresa de telecomunicaciones, utilizando variables relevantes del comportamiento y perfil del cliente.  
Se aplicaron técnicas de análisis exploratorio, preprocesamiento, modelado supervisado y visualización comparativa para identificar patrones de cancelación y proponer estrategias de retención.

---

## 🗂️ Estructura del Proyecto
Extracción
**Eliminación de columnas irrelevantes**
  Encoding
  Verificación de la Proporcion de Cancelación (Churn)
  Balanceo de Clases
  Normalización y estandarización
**CORRELACION Y SELECCIÓN DE VARIABLES**
  Análisis de correlación
  Analisis Dirigido
**MODELADO PREDICTIVO**
  Separación de Datos
  Creación de Modelos
  ¿Por qué normalizar los datos?
  Evaluación de Modelos
  Comparación de desempeño entre modelos
**INTERPRETACIÓN Y CONCLUSIONES**
  Analisis de la Importancia de las Variables
  CONCLUSIÓN
  Informe Final: Análisis de Cancelación de Clientes y Estrategias de Retención

##  Preparación de los Datos

### Clasificación de Variables

- **Numéricas:** `tenure`, `MonthlyCharges`, `TotalCharges` (eliminada por inconsistencias)
- **Categóricas:** `Contract`, `InternetService`, `PaymentMethod`, `OnlineSecurity`, entre otras

### Transformaciones Aplicadas

- **Codificación:**  
  Variables categóricas fueron transformadas mediante `pd.get_dummies()` con `drop_first=True` para evitar multicolinealidad.
  
- **Normalización:**  
  Se aplicó `StandardScaler` a variables numéricas para modelos sensibles a escala (Regresión Logística, SVM, KNN).

### ✂División de Datos

- Se utilizó `train_test_split` con `stratify=y` para mantener la proporción de cancelaciones.
- División 80/20 entre entrenamiento y prueba.

----

## Modelos Aplicados y Justificaciones

- **Regresión Logística:**  
  Modelo interpretable, útil para entender el impacto de cada variable. Requiere normalización.

- **Random Forest:**  
  Modelo robusto, no sensible a escala. Permite extraer importancia de variables.

- **KNN:**  
  Basado en distancia, sensible a escala. Útil para entender proximidad entre clientes.

- **SVM Lineal:**  
  Separación clara entre clases. Requiere normalización para definir correctamente el hiperplano.

> Se aplicó validación cruzada y balanceo de clases (SMOTE) para mejorar la detección de la clase minoritaria (`Churn`).

---

## 🚀 Instrucciones para Ejecutar el Cuaderno

1. **Instalar bibliotecas necesarias:**

instalar pandas numpy matplotlib seaborn scikit-learn

2. **Cargar el dataset tratado:**

import pandas as pd
df = pd.read_csv('data/datos_tratados1.csv')
3. 
4. **Sigue el flujo desde la carga de datos, EDA, preprocesamiento, modelado y evaluación.**
