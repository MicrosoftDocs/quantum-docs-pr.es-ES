---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: Operación IterateThroughCartesianPower
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 3a303d13c4a6f102dab92d814e24df9d90213fbe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840295"
---
# <a name="iteratethroughcartesianpower-operation"></a>Operación IterateThroughCartesianPower

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>Ejemplo

Dada una operación `op` , los dos fragmentos de código siguientes son equivalentes:

```qsharp
IterateThroughCartesianPower(2, 3, op);
```

```qsharp
op([0, 0]);
op([1, 0]);
op([2, 0]);
op([0, 1]);
// ..
op([2, 2]);
```

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. IterateThroughCartesianProduct](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)