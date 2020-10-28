---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 20a8c9ccf931261f7bc6e347ccc144c92f0d0545
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728871"
---
# <a name="ccontrolledca-function"></a>CControlledCA función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Dada una operación OP, devuelve una nueva operación que aplica el operador OP si un bit de control clásico es true. Si es `false` , no sucede nada.
El modificador `CA` indica que la operación es controlable y adjointable.

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit-ctl--adj"></a>OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de> CTL + ADJ

Operación que se va a aplicar condicionalmente.



## <a name="output--boolt--unit-ctl--adj"></a>Salida: ([bool](xref:microsoft.quantum.lang-ref.bool), ' t) => de la [unidad](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ

Nueva operación que es operativa si el bit de control clásico es true.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la operación que se va a aplicar condicionalmente.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)