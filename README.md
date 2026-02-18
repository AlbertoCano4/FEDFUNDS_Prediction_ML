# 📈 U.S. Federal Funds Rate Forecasting using Machine Learning

Este proyecto implementa un marco robusto de Machine Learning para el pronóstico de series temporales del **Tipo de Interés de la Reserva Federal (FEDFUNDS)**. El sistema entrena, evalúa y compara múltiples modelos econométricos y de ML para identificar la herramienta de predicción óptima basada en variables macroeconómicas de EE. UU.

## 🎯 Objetivo del Proyecto
El objetivo principal es construir y comparar rigurosamente modelos predictivos —lineales, no lineales y de series temporales— para anticipar el valor de **FEDFUNDS** del mes siguiente. Se busca identificar el modelo con mayor capacidad de generalización mediante métricas de error (MSE, MAE) y bondad de ajuste ($R^2$).

## 📊 Datos y Variables
El dataset utilizado contiene **795 observaciones mensuales** (desde 1959 hasta 2023). 

| Variable | Descripción | Rol |
| :--- | :--- | :--- |
| **FEDFUNDS** | Tipos de interés de la FED | **Target (y)** |
| **GS10** | Bono del Tesoro a 10 años | Feature (X) |
| **CPIAUCSL** | Índice de Precios al Consumidor (Inflación) | Feature (X) |
| **Unemployment** | Tasa de desempleo | Feature (X) |
| **POP** | Población total de EE. UU. | Feature (X) |
| **NA000334Q** | Producto Interior Bruto (PIB) | Feature (X) |
| **PCE** | Gastos de consumo personal | Feature (X) |

## 🛠️ Metodología y Modelos
El proyecto sigue un flujo de trabajo de ciencia de datos completo:
1. **Preprocesamiento**: Manejo de índices temporales y escalado de variables.
2. **Validación**: Split 80/20 (Train/Test) y **Cross-Validation (K-Fold)** para evitar el sobreajuste.
3. **Optimización**: Búsqueda de hiperparámetros ($\alpha$) para modelos Ridge y Lasso.

### Modelos Evaluados:
* **Lineales**: Regresión Lineal (OLS), Ridge (L2) y Lasso (L1).
* **No Lineales**: Random Forest Regressor, K-Nearest Neighbors (KNN) y **Gradient Boosting**.
* **Series Temporales**: Modelo **SARIMAX** para capturar estacionalidad y autocorrelación.

## ⚙️ Características Técnicas Clave
* **Selección de Características**: Uso de penalización Lasso para identificar las variables macro más influyentes.
* **Comparativa de Métricas**: Evaluación exhaustiva en el conjunto de test para medir la robustez real del modelo.
* **Función de Predicción**: El código incluye una función interactiva que permite obtener la predicción de la FED para cualquier mes y año específico del dataset.

## 🚀 Resultados Finales
* **Mejor Modelo Lineal**: Ridge Regression (mostrando mayor estabilidad frente a la multicolinealidad).
* **Mejor Modelo Global**: Los modelos de ensamble (**Random Forest** y **Gradient Boosting**) demostraron una precisión superior al capturar las relaciones no lineales entre la inflación, el empleo y los tipos de interés.

## 👥 Autores
* Alberto Cano
* Ignacio Fernández
* Iván Mier
* Gonzalo Ruiz
