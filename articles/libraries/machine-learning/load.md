---
title: Carga de datos de clásica
description: Aprenda a cargar su propio conjunto de información para entrenar un modelo clasificador con el Microsoft Quantum Development Kit (QDK).
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
ms.openlocfilehash: efa4a65a489446cbef48507d0b02a932da74c71c
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327669"
---
# <a name="load-and-classify-your-own-datasets"></a>Carga y clasificación de sus propios conjuntos de valores

En este breve tutorial, vamos a aprender a cargar su propio conjunto de información para entrenar un modelo clasificador con Quantum Development Kit (QDK).

Se recomienda encarecidamente el uso de un formato de serialización normalizado, como [archivos JSON](https://en.wikipedia.org/wiki/JSON) , para almacenar los datos.
Estos formatos ofrecen una alta compatibilidad con marcos diferentes como Python y el ecosistema de .NET.
En concreto, se recomienda usar nuestra plantilla para cargar los datos, para que pueda copiar y pegar el código directamente desde los ejemplos.

## <a name="template-for-loading-your-datasets"></a>Plantilla para cargar los conjuntos de valores

Supongamos que tenemos un conjunto de elementos de entrenamiento $ (x, y) $ de size $N = $2, donde cada instancia $x _i $ de $x $ tiene tres características: $x _ {I1} $, $x _ {I2} $ y $x _ {i3} $.
El conjunto de de validación tiene la misma estructura.
Estos conjuntos se pueden representar con un `data.json` archivo similar al siguiente:

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a>Ejemplo de uso de la plantilla

Supongamos que tenemos un conjunto de filas pequeño con los altos y pesos de los distintos gatos y perros. Este conjunto de DataSet es muy pequeño para entrenar un modelo, pero lo suficiente como para mostrar el proceso de carga de un conjunto de DataSet.

| Alto (m) | Peso (kg) | Animal |
|-----------|------------|--------|
| 0,54      | 30         | Foto    |
| 0,30      | 8          | Catalítica    |
| 0,91      | 44         | Foto    |
| 0,86      | 31          | Foto    |
| 0,32      | 5         | Catalítica    |
| 0,25      | 4          | Catalítica    |

El proceso es:

- En primer lugar, es necesario separar el conjunto de conocimientos en entrenamiento y validación. En este caso, podemos realizar solo los tres primeros ejemplos de entrenamiento y el resto de ejemplos para la validación. En general, se recomienda obtener un ejemplo aleatorio del conjunto de datos de entrenamiento y validación para evitar los sesgos no deseados en los datos de entrenamiento.
- En segundo lugar, es necesario asignar una etiqueta numérica a cada clase. Tenga en cuenta que, por el momento, la biblioteca QML solo tiene problemas de clasificación binaria. Por lo tanto, asignaremos la etiqueta 0 a la clase `Dog` y el número 1 a la clase `Cat` .
- Por último, se rellena la plantilla con los datos del conjunto de datos. Tenga en cuenta que para conjuntos de datos grandes, debe crear un script pequeño para generar automáticamente la plantilla a partir de su conjunto de datos concreto. Este script dependerá del formato original del conjunto de DataSet.

Para nuestro conjunto de `data.json` archivos, el archivo es:

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a>Carga de los datos

Una vez que los datos se serializan como un archivo JSON, puede cargarlos en mediante las bibliotecas JSON proporcionadas con el lenguaje de host que prefiera.

### <a name="python"></a>[Python](#tab/tabid-python)

Python proporciona el [ `json` paquete integrado](https://docs.python.org/3.7/library/json.html) para trabajar con datos serializados de JSON:

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[C#](#tab/tabid-csharp)

La plataforma .NET Core proporciona el [ `System.Text.Json` paquete](https://www.nuget.org/packages/System.Text.Json) para trabajar con datos serializados de JSON:

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a>Pasos siguientes

Ahora ya está listo para empezar a ejecutar sus propios experimentos con sus propios conjuntos de valores. Pruebe diferentes clasificadores y conjuntos de archivos y contribuya a la comunidad compartiendo sus resultados.
