---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 668ab89ed45c49d33ce50ff5d892f4d57246c12a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196368"
---
# <a name="inferredlabels-function"></a>InferredLabels función)

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Dada una matriz de probabilidades de clasificación y una diferencia, devuelve la etiqueta deducida de cada probabilidad.

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a>Entrada

### <a name="bias--double"></a>bias: [Double](xref:microsoft.quantum.lang-ref.double)

La diferencia entre dos clases, normalmente el resultado de entrenar un clasificador.


### <a name="probabilities--double"></a>probabilidades: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matriz de probabilidades de clasificación para un conjunto de ejemplos, normalmente resultante de la estimación de frecuencias de clasificación.



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)[]

La etiqueta deducida de cada probabilidad de clasificación.