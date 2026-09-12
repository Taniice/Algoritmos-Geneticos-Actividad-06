# Algoritmos Genéticos para Machine Learning


Este trabajo explora el uso de **algoritmos genéticos como técnicas de optimización aplicadas al aprendizaje automático**. Se desarrollan tres enfoques principales:

1. **Feature Selection:** utilizar algoritmos genéticos para encontrar las mejores características de un modelo de Machine Learning.
2. **Hyperparameter Optimization:** utilizar algoritmos genéticos para encontrar los mejores hiperparámetros de un modelo.
3. **Neuroevolution:** utilizar algoritmos genéticos para encontrar una arquitectura adecuada para una red neuronal.


## Dataset
Para los dos primeros experimentos se utilizó el dataset **Breast Cancer Wisconsin** y un modelo **Random Forest**.
* **Dataset:** Breast Cancer Wisconsin
* **Registros:** 569
* **Características:** 30
* **Clases:** 2
* **Datos de entrenamiento:** 455
* **Datos de prueba:** 114
* **Modelo:** Random Forest

---

## 1. Feature Selection

Se utilizó un algoritmo genético para encontrar un subconjunto de características que permita mantener o mejorar el rendimiento del modelo.

Cada individuo representa una combinación de características mediante un cromosoma binario:

* `1` → característica seleccionada
* `0` → característica descartada

La función fitness se calculó utilizando **Cross Validation**, buscando un buen rendimiento con una menor cantidad de características.

### Resultados

| Modelo                            | Características |   Accuracy |
| --------------------------------- | --------------: | ---------: |
| Random Forest                     |              30 |     0.9561 |
| Random Forest + Feature Selection |              15 | **0.9737** |

**Resultado:** se redujo el número de características de **30 a 15**, mientras que el accuracy aumentó de **0.9561 a 0.9737**.

---

## 2. Hyperparameter Optimization

Se utilizó un algoritmo genético para encontrar una combinación adecuada de hiperparámetros para Random Forest.

Los hiperparámetros optimizados fueron:

* `n_estimators`
* `max_depth`
* `min_samples_split`
* `min_samples_leaf`

### Mejores hiperparámetros encontrados

| Hiperparámetro      | Valor |
| ------------------- | ----: |
| `n_estimators`      |   150 |
| `max_depth`         |     8 |
| `min_samples_split` |     2 |
| `min_samples_leaf`  |     1 |

El mejor fitness obtenido durante la optimización fue **0.967** mediante Cross Validation.

### Resultados finales

| Modelo                   | Accuracy |
| ------------------------ | -------: |
| Random Forest base       |   0.9561 |
| Random Forest optimizado |   0.9474 |

La diferencia respecto al modelo base fue de **-0.0088**.

Aunque los hiperparámetros encontrados obtuvieron un buen resultado durante la validación cruzada, el rendimiento sobre el conjunto de prueba fue ligeramente inferior al modelo base.

---

## Conclusiones

* El **Feature Selection** obtuvo el mejor resultado del proyecto, reduciendo las características de 30 a 15 y aumentando el accuracy hasta **0.9737**.
* El **Hyperparameter Optimization** encontró una configuración con un fitness de **0.967**, aunque su accuracy final en el conjunto de prueba fue **0.9474**.
* Los experimentos muestran que los algoritmos genéticos pueden utilizarse como técnicas de búsqueda para optimizar diferentes componentes de un modelo de Machine Learning.
* Un mejor resultado durante la validación cruzada no necesariamente garantiza un mejor resultado sobre datos de prueba.

---
## 3. Neuroevolution: Optimización de una Red Neuronal

## Descripción

Este proyecto utiliza un **algoritmo genético** para encontrar una buena arquitectura de una red neuronal para clasificar la calidad de vinos.

El algoritmo prueba diferentes combinaciones de capas y neuronas y selecciona las arquitecturas con mejores resultados.

## Objetivo

Aplicar **Neuroevolution** para optimizar una red neuronal mediante:

* Selección
* Cruce
* Mutación
* Elitismo

## Dataset

Se utilizó el dataset **Wine Quality (Red Wine)** de UCI.

La variable `quality` se convirtió en dos clases:

* `0` → Calidad baja
* `1` → Calidad alta

## Algoritmo genético

Cada individuo representa una arquitectura de red neuronal.

Ejemplo:

```text
[32, 32, 16]
```

Esto representa:

* 32 neuronas en la primera capa oculta
* 32 neuronas en la segunda capa oculta
* 16 neuronas en la tercera capa oculta

El **fitness** corresponde al accuracy obtenido por la red neuronal.

## Resultado:

La mejor arquitectura encontrada fue:

```text
[32, 32, 16]
```

| Métrica   | Resultado |
| --------- | --------: |
| Accuracy  |    80.31% |
| Precision |    81.03% |
| Recall    |    82.46% |
| F1-Score  |    81.74% |

## Conclusión

El proyecto permitió aplicar **Neuroevolution** mediante un algoritmo genético para buscar una arquitectura adecuada de una red neuronal. A través de la selección, cruce, mutación y elitismo, se evaluaron diferentes combinaciones de capas y neuronas, obteniendo como mejor arquitectura `[32, 32, 16]` con un **accuracy de 80.31%**.

Los resultados muestran que los algoritmos genéticos pueden utilizarse como una alternativa para la **optimización de arquitecturas de redes neuronales**, evitando definir manualmente todas las combinaciones posibles.

## Tecnologías

* Python
* NumPy
* Pandas
* Scikit-learn
* Matplotlib
* Google Colab
  
## Ejecución

Abrir el archivo `ACTIVIDAD06.ipynb` en **Google Colab** y ejecutar las celdas.

