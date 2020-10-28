---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: Operación ApplySeriesOfOpsC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: d909aadbfe86f6d1314e9be5434249c40932ae4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729333"
---
# <a name="applyseriesofopsc-operation"></a>Operación ApplySeriesOfOpsC

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica una lista de operaciones y sus destinos secuencialmente en una matriz. Regula

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="listofops--t--unit-ctl"></a>listOfOps: ' t [] => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit) []

Lista de operaciones, cada una de las cuales toma una matriz ' t ' que se va a aplicar. Se aplican secuencialmente, el índice más bajo en primer lugar.
Cada debe tener un functor controlado


### <a name="targets--int"></a>destinos: [int](xref:microsoft.quantum.lang-ref.int)[] []

Matrices anidadas que describen los destinos de la operación. Cada matriz debe contener una lista de enteros que describen los índices que se van a utilizar.


### <a name="register--t"></a>registro: ' t []

Registro de qubit en el que se va a actuar.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)