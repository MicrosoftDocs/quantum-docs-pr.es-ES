---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e5975455385e182236d7e2864e26ca00795a40c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728876"
---
# <a name="ccontrolledc-function"></a>CControlledC función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Dada una operación OP, devuelve una nueva operación que aplica el operador OP si un bit de control clásico es true. Si es `false` , no sucede nada.
El modificador `C` indica que la operación es controlable.

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit-ctl"></a>OP: ' t => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)

Operación que se va a aplicar condicionalmente.



## <a name="output--boolt--unit-ctl"></a>Salida: ([bool](xref:microsoft.quantum.lang-ref.bool), ' t) => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)

Nueva operación que es operativa si el bit de control clásico es true.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la operación que se va a aplicar condicionalmente.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)