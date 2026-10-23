# 🐶 Pet Image Classifier

Proyecto desarrollado como parte del programa **AWS AI Programmer de Udacity**.

## 📋 Descripción

Este proyecto consiste en completar la implementación de una aplicación de clasificación de imágenes utilizando modelos preentrenados de redes neuronales convolucionales (*Convolutional Neural Networks*, CNN).

La estructura base del proyecto, los requisitos y el conjunto de datos fueron proporcionados por Udacity. El trabajo realizado consistió en implementar las funciones solicitadas, validar los resultados obtenidos y comparar el rendimiento de diferentes arquitecturas de redes neuronales convolucionales.

## 🎯 Objetivos

- Identificar correctamente qué imágenes corresponden a perros y cuáles no.
- Identificar correctamente la raza del perro en las imágenes clasificadas como perros.

## 🧠 Modelos evaluados

Se evaluaron las siguientes arquitecturas de redes neuronales convolucionales:

- **AlexNet**
- **ResNet**
- **VGG**

## 📊 Resultados

### 📁 Conjunto de datos evaluado

El conjunto de datos utilizado para la evaluación contiene un total de **40 imágenes**.

| Métrica | Valor |
|:---|---:|
| Total de imágenes | 40 |
| Imágenes de perros | 30 |
| Imágenes que no corresponden a perros | 10 |

### 📈 Resultados por arquitectura

A continuación, se presentan los resultados obtenidos por cada arquitectura evaluada:

| Arquitectura CNN | No perros correctos (%) | Perros correctos (%) | Razas correctas (%) | Coincidencia de etiquetas (%) |
|:---|---:|---:|---:|---:|
| ResNet | 90.0% | 100.0% | 90.0% | 82.5% |
| AlexNet | 100.0% | 100.0% | 80.0% | 75.0% |
| VGG | 100.0% | 100.0% | 93.3% | 87.5% |

## 🏆 Conclusión

De las tres arquitecturas evaluadas, **VGG obtuvo el mejor rendimiento general en el conjunto de datos utilizado**, destacando en la clasificación de imágenes y la identificación de razas.

Los resultados obtenidos por VGG fueron los siguientes:

- **100%** de clasificación correcta de imágenes de perros.
- **100%** de clasificación correcta de imágenes que no corresponden a perros.
- **93.3%** de clasificación correcta de razas.
- **87.5%** de coincidencia global de etiquetas.

Estos resultados muestran que VGG fue la arquitectura con mejor desempeño entre los modelos evaluados para este proyecto.

## 👨‍💻 Autor

**Jen Pierr Ismael Cieza Diaz**

Proyecto académico realizado durante el programa **AWS AI Programmer de Udacity**.
