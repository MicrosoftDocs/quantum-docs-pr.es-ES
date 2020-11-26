---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 08a62805f59df339ef6b91dff802c40c407808f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193019"
---
# <a name="discreteuniformdistribution-function"></a>DiscreteUniformDistribution función)

Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Devuelve una distribución uniforme en un intervalo inclusivo determinado.

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>Entrada

### <a name="min--int"></a>min: [int](xref:microsoft.quantum.lang-ref.int)

Entero más pequeño que se va a dibujar.


### <a name="max--int"></a>Max: [int](xref:microsoft.quantum.lang-ref.int)

Entero más grande que se va a dibujar.



## <a name="output--discretedistribution"></a>Salida: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Una distribución cuyos variates aleatorios son enteros en el intervalo inclusivo de `min` a `max` con probabilidad uniforme.

## <a name="remarks"></a>Observaciones

Se produce un error si `max <= min` .

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)