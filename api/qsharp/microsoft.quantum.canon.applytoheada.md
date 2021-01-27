---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: Operación ApplyToHeadA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 290347ff54492c4291db540e82cedcdd822a354e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850637"
---
# <a name="applytoheada-operation"></a>Operación ApplyToHeadA

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una operación al primer elemento de una matriz.

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a>Descripción

Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Head(targets))` .

## <a name="input"></a>Entrada

### <a name="op--t--unit--is-adj"></a>OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ

Operación que se va a aplicar.


### <a name="targets--t"></a>destinos: ' t []

Matriz de destinos a la que se aplicará el primer `op` .



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la operación que se va a aplicar.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyToHead](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [Microsoft. Quantum. Canon. ApplyToHeadC](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [Microsoft. Quantum. Canon. ApplyToHeadCA](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)