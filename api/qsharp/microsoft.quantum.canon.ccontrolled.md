---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: a155b00806b17258b3f87629659bc7d786e4e11d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728882"
---
# <a name="ccontrolled-function"></a>CControlled función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Dada una operación OP, devuelve una nueva operación que aplica el operador OP si un bit de control clásico es true. Si es `false` , no sucede nada.

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit"></a>OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de> 

Operación que se va a aplicar condicionalmente.



## <a name="output--boolt--unit"></a>Salida: ([bool](xref:microsoft.quantum.lang-ref.bool), ' t) = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Nueva operación que es operativa si el bit de control clásico es true.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la operación que se va a aplicar condicionalmente.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. CControlledC](xref:Microsoft.Quantum.Canon.CControlledC)
- [Microsoft. Quantum. Canon. CControlledA](xref:Microsoft.Quantum.Canon.CControlledA)
- [Microsoft. Quantum. Canon. CControlledCA](xref:Microsoft.Quantum.Canon.CControlledCA)