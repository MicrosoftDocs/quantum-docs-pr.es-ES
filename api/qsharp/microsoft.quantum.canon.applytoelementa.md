---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: Operación ApplyToElementA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: f34089c2a45de281507cb79bde8a8cb9d2fefe47
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729266"
---
# <a name="applytoelementa-operation"></a>Operación ApplyToElementA

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica una operación a un elemento determinado de una matriz.

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a>Descripción

Dada una operación `op` , `index` se aplica un índice y una matriz de destinos `targets` `op(targets[index])` .

## <a name="input"></a>Entrada

### <a name="op--t--unit-adj"></a>OP: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)

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