---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: Operación ApplySeriesOfOps
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: aff0bcb831960153166e88aef1f05e000125d5d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729344"
---
# <a name="applyseriesofops-operation"></a>Operación ApplySeriesOfOps

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica una lista de operaciones y sus destinos secuencialmente en una matriz.

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="listofops--t--unit-"></a>listOfOps: ' t [] = [unidad](xref:microsoft.quantum.lang-ref.unit)> []

Lista de operaciones, cada una de las cuales toma una matriz ' t ' que se va a aplicar. Se aplican secuencialmente, el índice más bajo en primer lugar.


### <a name="targets--int"></a>destinos: [int](xref:microsoft.quantum.lang-ref.int)[] []

Matrices anidadas que describen los destinos de la operación. Cada matriz debe contener una lista de enteros que describen los índices que se van a utilizar.


### <a name="register--t"></a>registro: ' t []

Registro de qubit en el que se va a actuar.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)