---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: Operación ApplyToHead
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 35f19cbb1090e974e18f338239764c9c8b854116
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217346"
---
# <a name="applytohead-operation"></a>Operación ApplyToHead

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una operación al primer elemento de una matriz.

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>Descripción

Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Head(targets))` .

## <a name="input"></a>Entrada

### <a name="op--t--unit"></a>OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de> 

Operación que se va a aplicar.


### <a name="targets--t"></a>destinos: ' t []

Matriz de destinos a la que se aplicará el primer `op` .



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la operación que se va a aplicar.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyToHeadA](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [Microsoft. Quantum. Canon. ApplyToHeadC](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [Microsoft. Quantum. Canon. ApplyToHeadCA](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)