---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operación DrawRandomInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733596"
---
# <a name="drawrandomint-operation"></a>Operación DrawRandomInt

Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)

Configura [](https://nuget.org/packages/)


Dibuja un entero aleatorio en un intervalo inclusivo determinado.

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a>Entrada

### <a name="min--int"></a>min: [int](xref:microsoft.quantum.lang-ref.int)

Entero más pequeño que se va a dibujar.


### <a name="max--int"></a>Max: [int](xref:microsoft.quantum.lang-ref.int)

Entero más grande que se va a dibujar.



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Un entero en el intervalo inclusivo de `min` a `max` con probabilidad uniforme.

## <a name="remarks"></a>Observaciones

Se produce un error si `max <= min` .

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. DiscreteUniformDistribution](xref:Microsoft.Quantum.DiscreteUniformDistribution)