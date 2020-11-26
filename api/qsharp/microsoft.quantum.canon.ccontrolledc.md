---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 25ac2b35047b1c33a89149eae6d40f6f7ae3b454
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216921"
---
# <a name="ccontrolledc-function"></a>CControlledC función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una operación OP, devuelve una nueva operación que aplica el operador OP si un bit de control clásico es true. Si es `false` , no sucede nada.
El modificador `C` indica que la operación es controlable.

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit--is-ctl"></a>OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL

Operación que se va a aplicar condicionalmente.



## <a name="output--boolt--unit--is-ctl"></a>Salida: ([bool](xref:microsoft.quantum.lang-ref.bool), ' t) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es CTL

Nueva operación que es operativa si el bit de control clásico es true.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la operación que se va a aplicar condicionalmente.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)