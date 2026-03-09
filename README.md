# 📉 Predicción de Evasión de Clientes (Churn) con Machine Learning

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat&logo=python)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine_Learning-orange?style=flat&logo=scikit-learn)
![Pandas](https://img.shields.io/badge/Pandas-Data_Processing-150458?style=flat&logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-Data_Visualization-3776AB?style=flat)

## 📖 Descripción del Proyecto
Este proyecto representa la **Fase 2** del análisis de clientes para la empresa ficticia **Telecom X**. Tras un análisis exploratorio inicial, el objetivo de este proyecto es desarrollar **modelos predictivos** capaces de prever con anticipación qué clientes tienen mayor probabilidad de cancelar su suscripción (Churn). 

Esto permite a la empresa pasar de una postura reactiva a una **estrategia de retención proactiva** basada en inteligencia de datos.

## 🛠️ Herramientas y Tecnologías
* **Lenguaje:** Python
* **Manipulación de Datos:** Pandas, NumPy
* **Visualización:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-Learn (Regresión Logística, Random Forest)
* **Balanceo de Datos:** Imbalanced-Learn (SMOTE)

## 🧠 Metodología (Pipeline de Machine Learning)

### 1. Preparación de Datos
* **Limpieza:** Eliminación de variables no predictivas (ej. `customerID`).
* **Encoding:** Transformación de variables categóricas (texto) a numéricas mediante *One-Hot Encoding* (`pd.get_dummies`), esencial para el procesamiento matemático.
* **Balanceo (SMOTE):** Se generaron datos sintéticos para equilibrar la clase minoritaria (clientes que cancelan), logrando una distribución 50/50 para un entrenamiento justo.

### 2. Entrenamiento y Evaluación
Se dividió el dataset en **80% para entrenamiento** y **20% para pruebas**. Se entrenaron y compararon dos modelos:
1. **Regresión Logística:** (Con datos previamente normalizados usando `StandardScaler`).
2. **Random Forest Classifier:** Modelo basado en múltiples árboles de decisión.

## 📊 Conclusiones e Insights

Tras evaluar los modelos utilizando matrices de confusión y métricas de clasificación (Accuracy, Precision, Recall, F1-Score):

* 🏆 **Modelo Ganador:** El algoritmo de **Random Forest** demostró el mejor desempeño, logrando una exactitud (Accuracy) del **84%** en datos de prueba y detectando exitosamente a la gran mayoría de los clientes en riesgo real.
* 🔍 **Factores Clave de Cancelación:** Al analizar la "Importancia de las Variables" (Feature Importance), el modelo reveló que el top 3 de factores que impulsan el abandono son:
  1. Antigüedad del cliente (`tenure`)
  2. Cargo mensual (`Charges.Monthly`)
  3. Gasto total acumulado (`Charges.Total`)

## 💡 Recomendaciones Estratégicas para Telecom X
1. **Intervención Temprana:** El riesgo es crítico en los primeros meses. Implementar un programa de *onboarding* robusto para fidelizar desde el día uno.
2. **Revisión de Precios Proactiva:** Utilizar el algoritmo para emitir alertas cuando el cargo mensual ponga a un cliente en "zona de riesgo", permitiendo al equipo de retención ofrecer ajustes de plan antes de la cancelación.
3. **Fidelización a Largo Plazo:** Incentivar la transición de contratos "mes a mes" (alto riesgo) a contratos anuales mediante beneficios exclusivos.

## ⚙️ Instrucciones de Uso

Si deseas ejecutar este análisis localmente, sigue estos pasos:

1. Clona este repositorio:
   ```bash
   git clone https://github.com/JociasOrt/ml-customer-churn-telecom.git
2. Instala las dependencias necesarias:
  `pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn`
3. Ejecuta el notebook principal `.ipynb` celda por celda. 
