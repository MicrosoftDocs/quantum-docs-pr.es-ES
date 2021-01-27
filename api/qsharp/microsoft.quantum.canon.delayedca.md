---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: c44e3448c471f2a20f995d4546ee54f3affb726e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840545"
---
# <a name="delayedca-function"></a>DelayedCA función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve una operación que aplica la operación dada con el argumento especificado.

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit--is-adj--ctl"></a>OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL

Operación que se va a aplicar como resultado de aplicar el valor devuelto.


### <a name="arg--t"></a>Arg: ' t

Entrada a la que `op` se aplica la operación.



## <a name="output--unit--unit--is-adj--ctl"></a>Salida: [](xref:microsoft.quantum.lang-ref.unit) => [unidad](xref:microsoft.quantum.lang-ref.unit) de unidad es ADJ + CTL

Una nueva operación que se aplica `op` con la entrada `arg`

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la operación que se va a retrasar.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. retrasado](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)