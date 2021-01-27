---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 576b4b1f11fc21476bbb019d4b0326981294528c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848407"
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