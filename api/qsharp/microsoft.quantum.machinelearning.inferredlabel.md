---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732372"
---
# <a name="inferredlabel-function"></a>InferredLabel función)

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Configura [](https://nuget.org/packages/)


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