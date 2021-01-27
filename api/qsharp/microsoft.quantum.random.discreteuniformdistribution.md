---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: f909e7def5439ec0feef4ca4dc0cf8ed12374dfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853715"
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

## <a name="example"></a>Ejemplo

El siguiente fragmento de código de Q # revierte aleatoriamente un dado de seis lados:

```qsharp
let dieDistribution = DiscreteUniformDistribution(1, 6);
let dieRoll = dieDistribution::Sample();
```

## <a name="remarks"></a>Observaciones

Se produce un error si `max <= min` .

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)