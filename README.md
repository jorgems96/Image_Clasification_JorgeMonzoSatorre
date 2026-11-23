# Clasificación de tumores pulmonares usando modelos de machine learning y deep learning

Cuaderno de Google Colab del Trabajo Fin de Grado de **Jorge Monzó Satorre** (Grado en Ingeniería
Biomédica, Universidad de Alicante, 2026).

- Tutor: David Gil Méndez (Dpto. Tecnología Informática y Computación)
- Cotutor: Jesús Peral Cortés (Dpto. Lenguajes y Sistemas Informáticos)

## Contenido

`clasificacion_tumores_pulmonares.ipynb` contiene el estudio piloto completo descrito en la memoria, con las
salidas de la ejecución de la que proceden las cifras y figuras del trabajo.

1. Descarga del dataset y análisis exploratorio.
2. Deduplicación en dos niveles (MD5 y *average hash* perceptual) y nuevo reparto estratificado
   en entrenamiento, validación y test.
3. E0. Control con un *Random Forest* entrenado solo con metadatos de adquisición.
4. E1. Modelo A, una CNN entrenada desde cero.
5. E2 y E3. Modelo B, ResNet50 preentrenada en ImageNet con *transfer learning*, con validación cruzada y
   evaluación en test.
6. E4. Explicabilidad con Grad-CAM y LIME.

## Datos

Se usa el *Chest CT-Scan Images Dataset* publicado en Kaggle por Mohamed Hany (2020), con cuatro
clases (adenocarcinoma, carcinoma de células grandes, carcinoma escamoso y tejido normal).

https://www.kaggle.com/datasets/mohamedhanyyy/chest-ctscan-images

El dataset no se incluye en este repositorio. El cuaderno lo descarga con `kagglehub`, para lo que
se necesita una cuenta de Kaggle. Las condiciones de uso son las indicadas en su página.

## Ejecución

1. Abrir el cuaderno en Google Colab y activar un entorno con GPU.
2. Ejecutar las celdas en orden. La semilla global es `SEED = 42`, la deduplicación perceptual
   está activada (`DEDUP_PERCEPTUAL = True`) y el volteo horizontal desactivado
   (`USAR_FLIP_HORIZONTAL = False`).

Las semillas favorecen la reproducibilidad, pero no garantizan resultados idénticos entre
ejecuciones. Con un conjunto de datos tan pequeño, una nueva ejecución puede dar cifras algo
distintas de las de la memoria, sobre todo en el Modelo A.

## Versiones

Entorno de Google Colab en la fecha del estudio piloto (agosto de 2026).

| Librería | Versión |
| --- | --- |
| Python | 3.12.13 |
| TensorFlow / Keras | 2.20.0 / 3.13.2 |
| scikit-learn | 1.6.1 |
| LIME | 0.2.0.1 |
| scikit-image | 0.25.2 |
| NumPy / pandas | 2.0.2 / 2.2.2 |
| Pillow | 11.3.0 |
| Matplotlib / seaborn | 3.10.0 / 0.13.2 |
| kagglehub | 1.0.2 |

## Cita

Monzó Satorre, J. (2026). *Clasificación de tumores pulmonares usando modelos de machine learning y
deep learning* [Trabajo Fin de Grado, Universidad de Alicante].
