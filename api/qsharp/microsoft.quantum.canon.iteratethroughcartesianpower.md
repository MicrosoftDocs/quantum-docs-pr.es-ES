---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: Operación IterateThroughCartesianPower
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 526d28cbf3cd356b4f48eec02b3f032f70a868d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728637"
---
# <a name="iteratethroughcartesianpower-operation"></a>Operación IterateThroughCartesianPower

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica una operación para cada índice en la potencia cartesiano de un intervalo de enteros.

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>Descripción

Aplica de forma iterativa una operación para cada elemento de una potencia cartesiano del intervalo `0..(bound - 1)` .

## <a name="input"></a>Entrada

### <a name="power--int"></a>potencia: [int](xref:microsoft.quantum.lang-ref.int)

La potencia cartesiano a la que `0..(bound - 1)` se debe elevar el intervalo.


### <a name="bound--int"></a>enlazado: [int](xref:microsoft.quantum.lang-ref.int)

Especificación del intervalo que se va a recorrer en iteración, dado como la longitud del intervalo.


### <a name="op--int--unit"></a>OP: [int](xref:microsoft.quantum.lang-ref.int)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Operación a la que se va a llamar para cada elemento de la potencia cartesiano dada.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. IterateThroughCartesianProduct](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)