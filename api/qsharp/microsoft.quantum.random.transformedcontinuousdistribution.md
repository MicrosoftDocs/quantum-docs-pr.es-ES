---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726459"
---
# <a name="transformedcontinuousdistribution-function"></a>TransformedContinuousDistribution función)

Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)

Configura [](https://nuget.org/packages/)


Dada una distribución continua, devuelve una nueva distribución que transforma el original por una función determinada.

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Entrada

### <a name="transform--double---double"></a>transformación: [doble](xref:microsoft.quantum.lang-ref.double) -> [doble](xref:microsoft.quantum.lang-ref.double)

Función que transforma variates de la distribución original en la distribución transformada.


### <a name="distribution--continuousdistribution"></a>distribución: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Distribución original que se va a transformar.



## <a name="output--continuousdistribution"></a>Salida: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Nueva distribución relacionada con `distribution` la transformación proporcionada por `transform` .