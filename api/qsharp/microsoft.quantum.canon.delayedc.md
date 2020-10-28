---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 7cfd77b0bb2d91c5a1c4bb5bc84e052421d733a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728720"
---
# <a name="delayedc-function"></a>DelayedC función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Devuelve una operación que aplica la operación dada con el argumento especificado.

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit-ctl"></a>OP: ' t => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)

Operación que se va a aplicar como resultado de aplicar el valor devuelto.


### <a name="arg--t"></a>Arg: ' t

Entrada a la que `op` se aplica la operación.



## <a name="output--unit--unit-ctl"></a>Salida: [Unit](xref:microsoft.quantum.lang-ref.unit) => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit) de unidad

Una nueva operación que se aplica `op` con la entrada `arg`

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la operación que se va a retrasar.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. retrasado](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)