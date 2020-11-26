---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: Operación ApplySeriesOfOpsA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: e5b3527507f79dcc77803ce01472856145df0e9f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217975"
---
# <a name="applyseriesofopsa-operation"></a>Operación ApplySeriesOfOpsA

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una lista de operaciones y sus destinos secuencialmente en una matriz. (Contiguo)

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit is Adj
```


## <a name="input"></a>Entrada

### <a name="listofops--t--unit--is-adj"></a>listOfOps: ' t [] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ []

Lista de operaciones, cada una de las cuales toma una matriz ' t ' que se va a aplicar. Se aplican secuencialmente, el índice más bajo en primer lugar.
Cada debe tener un functor injoin


### <a name="targets--int"></a>destinos: [int](xref:microsoft.quantum.lang-ref.int)[] []

Matrices anidadas que describen los destinos de la operación. Cada matriz debe contener una lista de enteros que describen los índices que se van a utilizar.


### <a name="register--t"></a>registro: ' t []

Registro de qubit en el que se va a actuar.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)