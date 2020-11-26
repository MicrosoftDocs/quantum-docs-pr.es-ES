---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operación DrawRandomInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192917"
---
# <a name="drawrandomint-operation"></a>Operación DrawRandomInt

Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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