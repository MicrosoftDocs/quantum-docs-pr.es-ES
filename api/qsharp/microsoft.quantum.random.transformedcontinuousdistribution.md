---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 353442a4245a9e20bb1e4c46d2e8a84d4c9534b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857767"
---
# <a name="transformedcontinuousdistribution-function"></a>TransformedContinuousDistribution función)

Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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

## <a name="example"></a>Ejemplo

Las dos distribuciones siguientes son idénticas:

```qsharp
let dist1 = ContinuousUniformDistribution(1.0, 2.0);
let dist2 = TransformedContinuousDistribution(
    PlusD(1.0, _),
    ContinuousUniformDistribution(0.0, 1.0)
);
```