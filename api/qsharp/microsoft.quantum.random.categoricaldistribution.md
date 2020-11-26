---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 2e3d9b17939d5a9a5bc5e7d89a843e0ff5a848ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210257"
---
# <a name="categoricaldistribution-function"></a>CategoricalDistribution función)

Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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