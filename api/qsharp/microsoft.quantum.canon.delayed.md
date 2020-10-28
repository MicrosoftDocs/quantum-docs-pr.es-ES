---
uid: Microsoft.Quantum.Canon.Delayed
title: Función retrasada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 820a38c2b4de2e0151d55bd88fb4f69567182f6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728738"
---
# <a name="delayed-function"></a>Función retrasada

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Devuelve una operación que aplica la operación dada con el argumento especificado.

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a>Entrada

### <a name="op--t--u"></a>OP: ' t => ' U 

Operación que se va a aplicar.


### <a name="arg--t"></a>Arg: ' t

Entrada a la que se aplica la operación.



## <a name="output--unit--u"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit) => ' U 

Una nueva operación que se aplica `op` con la entrada `arg`

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la operación que se va a retrasar.
### <a name="u"></a>' U

El tipo de valor devuelto de la operación que se va a retrasar.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. DelayedC](xref:Microsoft.Quantum.Canon.DelayedC)
- [Microsoft. Quantum. Canon. retrasado](xref:Microsoft.Quantum.Canon.DelayedA)
- [Microsoft. Quantum. Canon. DelayedCA](xref:Microsoft.Quantum.Canon.DelayedCA)
- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)