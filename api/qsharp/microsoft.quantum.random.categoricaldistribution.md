---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 756e9e95cac5554ab8f885dab7c47ac1b174c0f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732541"
---
# <a name="categoricaldistribution-function"></a>CategoricalDistribution función)

Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)

Configura [](https://nuget.org/packages/)


Devuelve una distribución de categorías discretas, en la que se especifica explícitamente la probabilidad de cada una de las listas finitas de determinados resultados.

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>Entrada

### <a name="probs--double"></a>sondeos: [Double](xref:microsoft.quantum.lang-ref.double)[]

Probabilidades para cada resultado de la distribución por categorías.
Es posible que estas probabilidades no estén normalizadas, pero no deben ser negativas.



## <a name="output--discretedistribution"></a>Salida: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Índice `i` con probabilidad `probs[i] / sum` , donde `sum` es la suma de `probs` especificada por `Fold(PlusD, 0.0, probs)` .