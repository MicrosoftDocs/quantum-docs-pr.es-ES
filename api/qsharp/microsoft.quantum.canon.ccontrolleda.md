---
uid: Microsoft.Quantum.Canon.CControlledA
title: CControlledA función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 30b5e3408fa6e5a79b2f3d63cccc11899c0405ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728877"
---
# <a name="ccontrolleda-function"></a>CControlledA función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Dada una operación OP, devuelve una nueva operación que aplica el operador OP si un bit de control clásico es true. Si es `false` , no sucede nada.
El modificador `A` indica que la operación es adjointable.

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit-adj"></a>OP: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)

Operación que se va a aplicar condicionalmente.



## <a name="output--boolt--unit-adj"></a>Salida: ([bool](xref:microsoft.quantum.lang-ref.bool), ' t) => ADJ de [unidad](xref:microsoft.quantum.lang-ref.unit)

Nueva operación que es operativa si el bit de control clásico es true.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la operación que se va a aplicar condicionalmente.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)