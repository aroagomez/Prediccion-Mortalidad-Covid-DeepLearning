# Prediccion de Mortalidad por COVID-19 mediante Deep Learning

Este proyecto aborda la predicción de la mortalidad diaria por COVID-19 en Euskadi (España) utilizando arquitecturas avanzadas de aprendizaje profundo. Se plantea como un problema de regresión supervisada basado en ventanas temporales, utilizando registros oficiales obtenidos de Open Data Euskadi.

## Arquitecturas Implementadas
El estudio realiza una comparativa exhaustiva entre diferentes modelos para capturar las dependencias secuenciales y espaciales de la pandemia:

* **Perceptrón Multicapa (MLP):** Modelo base para establecer una línea de referencia (baseline).
* **Redes Recurrentes (LSTM y GRU):** Optimizadas para gestionar la inercia temporal y las dependencias a largo plazo en series cronológicas.
* **Redes de Grafos Neuronales (GNN):** Un enfoque innovador para integrar la dimensión espacial, tratando las zonas de salud como nodos de un grafo interconectados por correlación funcional.

## Metodología y Tecnologías
* **Frameworks:** PyTorch para el desarrollo de los modelos de Deep Learning.
* **Procesamiento de datos:** Uso de ventanas temporales de 7 días para capturar la inercia de los contagios y fallecimientos.
* **Pipeline:** Incluye limpieza de datos (manejo de sparsity), normalización/escalado y evaluación de curvas de pérdida (Loss) para asegurar la convergencia.
* **Entorno:** Jupyter Notebooks para la experimentación y visualización de resultados.



## Conclusiones Destacadas
* Las redes **LSTM** demostraron ser las más robustas para gestionar la inercia temporal en escenarios de predicción global.
* El modelo **GNN** permitió un análisis granular por barrios, identificando patrones de propagación que los modelos tradicionales ignoran, aunque enfrentó desafíos de dispersión de datos (sparsity) en zonas con baja mortalidad.
* Se validó la importancia del diseño de la topología del grafo para capturar la conectividad real entre las diferentes zonas de salud de Euskadi.

## Estructura del Repositorio
* `Proyecto_AARN.ipynb`: Notebook principal con la carga de datos, arquitectura de los modelos y entrenamiento.
* `model.path`: Pesos del modelo entrenado (PyTorch).
* `/data`: Conjuntos de datos en formato JSON procesados desde Open Data Euskadi.
* `Predicciones_Covid.pdf`: Informe técnico detallado con el análisis de resultados y comparativa de modelos.
