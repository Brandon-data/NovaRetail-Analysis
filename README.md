NovaRetail+ — Análisis de correlaciones del comportamiento de clientes

English summary ↓

Análisis exploratorio y correlacional de 15,000 clientes de NovaRetail+, una plataforma de comercio electrónico en Latinoamérica, para responder una pregunta del equipo de Crecimiento y Retención:

¿Qué factores del comportamiento del cliente están más fuertemente asociados con el ingreso anual generado?

El análisis es correlacional, no causal: identifica asociaciones y documenta con claridad lo que no se puede afirmar.

Contenido del repositorio
novaretail_correlation_analysis.ipynb — notebook con el análisis completo (carga, limpieza, visualización, correlaciones, hallazgos, limitaciones y próximos pasos).
Dataset

novaretail_comportamiento_clientes_2024.csv: 15,000 clientes y 12 columnas (edad, nivel de ingreso, visitas, compras, gasto publicitario dirigido, satisfacción, membresía premium, abandono, dispositivo, región e ingreso anual). Sin valores nulos.

El dataset proviene de la plataforma del curso y no se incluye en este repositorio.

Etapas del análisis
Carga y exploración: estructura, tipos de datos y rangos.
Preparación y supuestos: conversión de edad a entero, proporción de ceros por columna y supuestos documentados (incluida la escala de interpretación de los coeficientes).
Visualización: heatmap de correlaciones y scatterplots de los pares relevantes.
Coeficientes: Pearson y Spearman (numérica–numérica), punto-biserial (binaria–numérica), V de Cramér (categórica–categórica) y razón de correlación (categórica–numérica).
Interpretación para el negocio: tres hallazgos, cada uno con evidencia, interpretación no causal, límites e implicación.
Limitaciones y próximos pasos.
Hallazgos principales
El ingreso anual se asocia casi por completo con el número de compras (Pearson 0.967, Spearman 0.968). La relación es casi mecánica: el 100% de los clientes sin compras tiene ingreso 0, y representan el 30.4% de la base.
Visitas y publicidad se asocian poco con el ingreso (0.34 y 0.20). El gasto publicitario acompaña más a las visitas (0.58), con posible causalidad inversa: podría asignarse más gasto a los clientes más activos.
Edad, nivel de ingreso, satisfacción, dispositivo y región no se asocian con el ingreso. La membresía premium muestra un ingreso promedio mayor (44.6 frente a 35.3), pero con una asociación muy débil (0.093), y es el único par con relación débil con el abandono (V de Cramér 0.120).
Cómo abrir y reproducir el notebook

Open In Colab

Abre el notebook con el botón de Colab (o descárgalo y ábrelo en Jupyter).
Descarga el dataset del curso y ajusta la ruta en la celda de carga (pd.read_csv).
Ejecuta las celdas en orden.
Herramientas

Python · pandas · NumPy · seaborn · matplotlib · SciPy

🇬🇧 English summary

NovaRetail+ Customer Behavior: Correlation Analysis is an exploratory, correlational analysis of 15,000 customers of a Latin American e-commerce platform, aimed at finding which behaviors are most associated with annual revenue. (The notebook and its commentary are written in Spanish.)

Data: 15,000 customers, 12 columns, no missing values. The dataset comes from a course platform and is not included in this repo.
Methods: Pearson and Spearman, point-biserial, Cramér's V and the correlation ratio (η), plus a heatmap and scatterplots.
Key findings:
Annual revenue is almost entirely associated with the number of purchases (r ≈ 0.97). The relationship is nearly mechanical: all customers with no purchases (30.4%) have zero revenue.
Visits and targeted ad spend are only weakly associated with revenue; ad spend follows visits (r ≈ 0.58), possibly through reverse causality.
Age, customer income level, satisfaction, device and region show no association with revenue. Premium membership shows a higher average revenue but a very weak association.
Limits: correlation is not causation; the analysis does not include segmentation by group or significance tests. These are listed in the notebook as next steps.
Tools: Python, pandas, NumPy, seaborn, matplotlib, SciPy.
Run it: open the notebook in Colab with the badge above, download the course dataset and adjust the path in the loading cell.
