# 🐶 Pet Image Classifier

Proyecto académico realizado como parte del programa Nanodegree **Future AWS AI Programmer de Udacity**.

## 📋 Descripción

Este proyecto consiste en completar la implementación de una aplicación de clasificación de imágenes utilizando modelos preentrenados de redes neuronales convolucionales (*Convolutional Neural Networks*, CNN).

La estructura base del proyecto, los requisitos y el conjunto de datos fueron proporcionados por Udacity. El trabajo realizado consistió en implementar las funciones requeridas para procesar imágenes, clasificar mascotas, calcular estadísticas de rendimiento y comparar distintas arquitecturas de *Deep Learning*.

## 🎯 Objetivos del proyecto

El proyecto tenía dos objetivos principales:

1. Identificar correctamente qué imágenes corresponden a perros y cuáles no.
2. Clasificar correctamente la raza de los perros detectados.

## 🧠 Modelos evaluados

Se compararon las siguientes arquitecturas CNN preentrenadas:

- **AlexNet**
- **ResNet**
- **VGG**

## 🛠️ Tecnologías utilizadas

- Python
- Deep Learning
- Convolutional Neural Networks (CNN)
- Transfer Learning
- ImageNet
- Bash

---

## 📁 Conjuntos de datos utilizados

### `pet_images`

Conjunto de datos proporcionado por Udacity para la evaluación principal.

| Métrica | Valor |
|:---|---:|
| Total de imágenes | 40 |
| Imágenes de perros | 30 |
| Imágenes que no corresponden a perros | 10 |

### `uploaded_images`

Conjunto de imágenes adicionales utilizado para responder las preguntas finales del proyecto y validar el comportamiento de los modelos sobre ejemplos externos al conjunto principal.

Incluye:

- 2 imágenes de Saint Bernard.
- 1 imagen de un oso.
- 1 imagen de un vaso.

---

## 🚀 Ejecución

### Ejecutar un modelo específico

**ResNet**

```bash
python check_images.py --dir pet_images/ --arch resnet --dogfile dognames.txt
```

**AlexNet**

```bash
python check_images.py --dir pet_images/ --arch alexnet --dogfile dognames.txt
```

**VGG**

```bash
python check_images.py --dir pet_images/ --arch vgg --dogfile dognames.txt
```

---

## ⚙️ Automatización de pruebas

### Evaluación del conjunto principal

```bash
sh run_models_batch.sh
```

Este script ejecuta automáticamente los tres modelos sobre las imágenes contenidas en `pet_images` y genera los siguientes archivos:

```text
alexnet_pet-images.txt
resnet_pet-images.txt
vgg_pet-images.txt
```

Cada archivo contiene:

- Resultados de clasificación.
- Estadísticas calculadas.
- Porcentajes de precisión.
- Imágenes clasificadas incorrectamente.
- Tiempo de ejecución.

### Evaluación de imágenes adicionales

```bash
sh run_models_batch_uploaded.sh
```

Este script ejecuta los tres modelos sobre las imágenes almacenadas en `uploaded_images` y genera los siguientes archivos:

```text
alexnet_uploaded-images.txt
resnet_uploaded-images.txt
vgg_uploaded-images.txt
```

Los resultados obtenidos fueron utilizados para responder las preguntas finales del proyecto.

---

# 📊 Resultados

## Resultados por arquitectura

| Arquitectura CNN | No perros correctos (%) | Perros correctos (%) | Razas correctas (%) | Coincidencia de etiquetas (%) |
|:---|---:|---:|---:|---:|
| AlexNet | 100.0% | 100.0% | 80.0% | 75.0% |
| ResNet | 90.0% | 100.0% | 90.0% | 82.5% |
| VGG | 100.0% | 100.0% | 93.3% | 87.5% |

## ⏱️ Tiempo de ejecución

| Modelo | Tiempo de ejecución |
|:---|---:|
| AlexNet | 2 segundos |
| ResNet | 5 segundos |
| VGG | 19 segundos |

---

# 🔍 Análisis de resultados

## Objetivo 1: Identificar perros y no perros

Tanto **AlexNet** como **VGG** identificaron correctamente todas las imágenes de perros y no perros del conjunto de datos principal, alcanzando una precisión del **100%** en ambas categorías.

**ResNet** obtuvo una precisión del **90%** en la clasificación de imágenes que no correspondían a perros y del **100%** en la identificación de imágenes de perros.

## Objetivo 2: Clasificar correctamente las razas

La clasificación de razas mostró diferencias más significativas entre los modelos:

| Modelo | Precisión en la clasificación de razas |
|:---|---:|
| AlexNet | 80.0% |
| ResNet | 90.0% |
| VGG | 93.3% |

AlexNet presentó más errores en la identificación de razas, mientras que ResNet mejoró considerablemente este resultado. VGG obtuvo la mayor precisión en esta categoría.

## Relación entre precisión y rendimiento

Los tiempos de ejecución muestran el compromiso entre precisión y velocidad de procesamiento:

- **AlexNet** fue el modelo más rápido.
- **ResNet** ofreció un equilibrio adecuado entre precisión y rendimiento.
- **VGG** logró la mayor precisión, aunque necesitó más tiempo de procesamiento.

---

# 🧪 Validación con imágenes adicionales

Las imágenes de la carpeta `uploaded_images` se utilizaron para responder las preguntas finales planteadas por el proyecto.

Las pruebas permitieron verificar:

- La consistencia de clasificación de una misma raza.
- El comportamiento del modelo frente a una imagen invertida.
- La correcta identificación de imágenes que no correspondían a perros.

### Resultados observados

- Los tres modelos clasificaron correctamente las dos imágenes de Saint Bernard.
- Los tres modelos identificaron correctamente la imagen invertida como la misma raza.
- Los tres modelos identificaron correctamente el oso y el vaso como imágenes que no correspondían a perros.
- Todos los modelos obtuvieron un **100% de precisión** en la identificación de perros, razas y no perros en este conjunto reducido de pruebas.

### Selección del modelo para las pruebas adicionales

Dado que AlexNet, ResNet y VGG obtuvieron los mismos resultados de clasificación sobre las imágenes adicionales, **ResNet fue considerado la mejor alternativa práctica**, al combinar los resultados obtenidos con un menor tiempo de ejecución que VGG.

---

# 🏆 Conclusiones

Los resultados obtenidos coincidieron con los resultados de referencia proporcionados por Udacity.

Para el conjunto principal de evaluación:

- **AlexNet** destacó por su velocidad.
- **ResNet** ofreció un buen equilibrio entre precisión y rendimiento.
- **VGG** obtuvo el mejor desempeño general.

VGG fue la arquitectura con mejores resultados globales, alcanzando:

- **100%** de clasificación correcta de perros.
- **100%** de clasificación correcta de imágenes que no correspondían a perros.
- **93.3%** de clasificación correcta de razas.
- **87.5%** de coincidencia global de etiquetas.

En conclusión, VGG fue el modelo con mejor rendimiento general en el conjunto principal de evaluación, mientras que ResNet representó una alternativa interesante para las pruebas adicionales debido a su menor tiempo de ejecución frente a VGG.

---

## 📚 Aprendizajes

Durante el desarrollo del proyecto se trabajó con los siguientes conceptos y herramientas:

- Diccionarios en Python.
- Procesamiento de imágenes.
- Argumentos por línea de comandos.
- Modelos CNN preentrenados.
- Cálculo de métricas de clasificación.
- Comparación de arquitecturas de Deep Learning.
- Automatización de pruebas mediante scripts Bash.

---

## 👨‍💻 Autor

**Jen Pierr Ismael Cieza Diaz**

Proyecto académico realizado como parte del programa **AWS AI Programmer de Udacity**.
