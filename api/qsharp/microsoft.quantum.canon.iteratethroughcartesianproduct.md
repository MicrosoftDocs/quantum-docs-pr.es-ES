---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: Operación IterateThroughCartesianProduct
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: a0aaa8ef6aa6798d31c810254c92820f8136800c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840279"
---
# <a name="iteratethroughcartesianproduct-operation"></a>Operación IterateThroughCartesianProduct

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>Ejemplo

Dada una operación `op` , los dos fragmentos de código siguientes son equivalentes:

```qsharp
IterateThroughCartesianProduct([3, 4, 5], op);
```

```qsharp
op([0, 0, 0]);
op([1, 0, 0]);
op([2, 0, 0]);
op([0, 1, 0]);
// ...
op([0, 3, 0]);
op([0, 0, 1]);
//
op([2, 3, 4]);
```

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. IterateThroughCartesianPower](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)