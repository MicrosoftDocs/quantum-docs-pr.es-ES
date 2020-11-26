---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: a3911fe9962ce18daa239de0272c53d83344134a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193087"
---
# <a name="continuousuniformdistribution-function"></a>ContinuousUniformDistribution función)

Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Devuelve una distribución uniforme en un intervalo inclusivo determinado.

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Entrada

### <a name="min--double"></a>min: [doble](xref:microsoft.quantum.lang-ref.double)

Número real más pequeño que se va a dibujar.


### <a name="max--double"></a>máx.: [doble](xref:microsoft.quantum.lang-ref.double)

Número real más grande que se va a dibujar.



## <a name="output--continuousdistribution"></a>Salida: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Una distribución cuyos variates aleatorios son números reales en el intervalo inclusivo de `min` a `max` con probabilidad uniforme.

## <a name="remarks"></a>Observaciones

Se produce un error si `max <= min` .

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)