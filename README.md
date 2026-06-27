# Actividad 6

# 🩺 Evaluación y Validación de Modelos de Machine Learning para la Clasificación de Cáncer de Piel

## 📌 Descripción del proyecto

Este proyecto desarrolla un sistema de **Machine Learning supervisado** para la clasificación de lesiones cutáneas como **no sospechosas** o **sospechosas de malignidad**, utilizando únicamente **características clínicas y morfológicas previamente extraídas**, sin emplear técnicas de Deep Learning ni procesamiento de imágenes.

El objetivo principal consiste en evaluar y validar diferentes algoritmos de clasificación mediante métricas de desempeño, validación cruzada, análisis estadístico y curvas ROC, siguiendo un flujo completo de evaluación de modelos de Machine Learning.

---

# Objetivo

Desarrollar y evaluar modelos supervisados de Machine Learning capaces de clasificar lesiones cutáneas utilizando características clínicas y morfológicas, obteniendo un desempeño superior mediante métricas de clasificación y validando su capacidad de generalización mediante validación cruzada estratificada, análisis ROC-AUC y pruebas estadísticas.

---

# Dataset

Se utilizó el **PAD-UFES-20 Metadata Dataset**, un conjunto de datos clínicos de lesiones cutáneas.

### Variables utilizadas

* Edad
* Sexo
* Localización anatómica
* Diámetro de la lesión
* Tipo de piel (Fitzpatrick)
* Historial de cáncer de piel
* Historial familiar
* Prurito
* Sangrado
* Dolor
* Crecimiento
* Elevación
* Otras características clínicas

Las lesiones fueron agrupadas en dos clases:

* **0:** Lesión no sospechosa
* **1:** Lesión sospechosa de malignidad

Esta simplificación permite desarrollar un sistema de apoyo para el tamizaje dermatológico.

---

# Modelos implementados

Se evaluaron tres algoritmos de clasificación supervisada:

* Regresión Logística
* Random Forest
* Gradient Boosting

---

# Metodología

El flujo de trabajo desarrollado fue el siguiente:

1. Carga del dataset.
2. Análisis exploratorio de datos (EDA).
3. Limpieza e imputación de valores faltantes.
4. Codificación de variables categóricas.
5. División entrenamiento/prueba.
6. Entrenamiento de modelos.
7. Evaluación mediante:

   * Accuracy
   * Precision
   * Recall
   * F1-score
   * ROC-AUC
8. Matriz de confusión.
9. Ajuste del umbral de decisión.
10. Validación cruzada estratificada (5-Fold).
11. Curvas ROC utilizando predicciones obtenidas mediante `cross_val_predict()`.
12. Comparación entre modelos.
13. Escenario de prueba A/B.
14. Análisis de significancia estadística (Wilcoxon).
15. Registro de experimentos.

---

# Métricas evaluadas

* Accuracy
* Precision
* Recall
* F1-score
* ROC-AUC

La métrica de mayor interés fue **Recall**, debido a que en aplicaciones médicas resulta prioritario minimizar los falsos negativos para evitar que lesiones potencialmente malignas no sean detectadas.

---

# Validación del modelo

La capacidad de generalización de los modelos se evaluó mediante:

* Validación cruzada estratificada (5-Fold)
* Curvas ROC basadas en predicciones fuera de muestra
* Comparación entre modelos
* Prueba estadística de Wilcoxon

---

# Resultados

El modelo con mejor desempeño fue **Gradient Boosting**, obteniendo el mejor equilibrio entre:

* Accuracy
* Precision
* Recall
* F1-score
* ROC-AUC

La validación cruzada mostró un comportamiento consistente entre las diferentes particiones del conjunto de datos, indicando una adecuada capacidad de generalización.

---

# Estructura del proyecto

```text
Proyecto_Cancer_Piel/
│
├── metadata.csv
├── notebook_cancer_piel_ml.ipynb
├── reporte_tecnico_cancer_piel_ml.docx
├── tablero_visual_cancer_piel_ml.pdf
├── resultados/
│   ├── confusion_matrix.png
│   ├── roc_curve.png
│   ├── metricas.csv
│   └── feature_importance.csv
│
├── README.md
└── requirements.txt
```

---

# Tecnologías utilizadas

* Python
* Pandas
* NumPy
* Scikit-learn
* XGBoost
* Matplotlib
* SciPy

---

# Conclusiones

Los modelos de Machine Learning demostraron ser herramientas eficaces para apoyar la clasificación de lesiones cutáneas utilizando únicamente variables clínicas y morfológicas.

El análisis de métricas, la validación cruzada y las curvas ROC mostraron un desempeño consistente del modelo seleccionado, evidenciando un adecuado equilibrio entre precisión y sensibilidad.

Este tipo de modelos puede contribuir como herramienta de apoyo al proceso diagnóstico, aunque su implementación clínica requeriría validación adicional utilizando bases de datos externas y poblaciones independientes.

---

# Autor

**Jesús Manuel Núñez López**

Materia: **Gestión de Proyectos de Inteligencia Artificial**

Actividad 6 – Junio 2026.
