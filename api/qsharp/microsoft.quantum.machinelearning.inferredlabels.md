---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 874d1a2f7cc6d67567e0d2baa70b0d26b639a029
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732349"
---
# <a name="inferredlabels-function"></a>InferredLabels función)

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Configura [](https://nuget.org/packages/)


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