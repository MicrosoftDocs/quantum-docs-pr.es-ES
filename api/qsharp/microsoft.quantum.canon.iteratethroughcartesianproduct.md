---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: Operación IterateThroughCartesianProduct
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: e4fc71f6f707639f6f89eece8546ec2fb434a15a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728643"
---
# <a name="iteratethroughcartesianproduct-operation"></a>Operación IterateThroughCartesianProduct

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica una operación para cada índice del producto cartesiano de varios intervalos.

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>Descripción

Aplica de forma iterativa una operación para cada elemento del producto cartesiano de `0..(bounds[0] - 1)` , `0..(bounds[1] - 1)` ,... `0..(bounds[Length(bounds) - 1] - 1)`

## <a name="input"></a>Entrada

### <a name="bounds--int"></a>límites: [int](xref:microsoft.quantum.lang-ref.int)[]

Una matriz que especifica los intervalos en los que se va a recorrer en iteración, donde cada intervalo se especifica como una longitud entera.


### <a name="op--int--unit"></a>OP: [int](xref:microsoft.quantum.lang-ref.int)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Operación a la que se va a llamar para cada elemento del producto cartesiano determinado.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. IterateThroughCartesianPower](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)