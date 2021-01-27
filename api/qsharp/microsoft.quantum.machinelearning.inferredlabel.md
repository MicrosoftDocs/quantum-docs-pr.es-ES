---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 46b24c283a01e6ac1c959ee4a6899591ee708ff7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848414"
---
# <a name="inferredlabel-function"></a>InferredLabel función)

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Dado una de probabilidad de clasificación y una diferencia, devuelve la etiqueta deducida de esa probabilidad.

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a>Entrada

### <a name="bias--double"></a>bias: [Double](xref:microsoft.quantum.lang-ref.double)

La diferencia entre dos clases, normalmente el resultado de entrenar un clasificador.


### <a name="probability--double"></a>probabilidad: [doble](xref:microsoft.quantum.lang-ref.double)

Una probabilidad de clasificación para un ejemplo determinado, que normalmente resulta de la estimación de la frecuencia de clasificación.



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

La etiqueta deducida de la probabilidad de clasificación dada.