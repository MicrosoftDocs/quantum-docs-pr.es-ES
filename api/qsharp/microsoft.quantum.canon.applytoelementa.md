---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: Operación ApplyToElementA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: e8318a7873476ee49d8e1e235e6c917a38ee6200
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208880"
---
# <a name="applytoelementa-operation"></a>Operación ApplyToElementA

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una operación a un elemento determinado de una matriz.

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit is Adj
```


## <a name="description"></a>Descripción

Dada una operación `op` , `index` se aplica un índice y una matriz de destinos `targets` `op(targets[index])` .

## <a name="input"></a>Entrada

### <a name="op--t--unit--is-adj"></a>OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ

Operación que se va a aplicar.


### <a name="index--int"></a>Índice: [int](xref:microsoft.quantum.lang-ref.int)

Índice en la matriz de destinos.


### <a name="targets--t"></a>destinos: ' t []

Matriz de destinos posibles para `op` .



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la operación que se va a aplicar.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyToElement](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [Microsoft. Quantum. Canon. ApplyToElementC](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [Microsoft. Quantum. Canon. ApplyToElementCA](xref:Microsoft.Quantum.Canon.ApplyToElementCA)