---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 05df99dce8b167f32078ce256748647ceb94d0fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851985"
---
# <a name="uncurriedopc-function"></a>UncurriedOpC función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una función que devuelve operaciones, devuelve una nueva operación que toma ambas entradas como una tupla.
El modificador `C` indica que las operaciones se pueden controlar.

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a>Entrada

### <a name="curriedop--t---u--unit--is-ctl"></a>curriedOp: ' U = > [unidad](xref:microsoft.quantum.lang-ref.unit)  de> es CTL

Función que devuelve las operaciones.



## <a name="output--tu--unit--is-ctl"></a>Salida: (' t, ' U) => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL

Una nueva operación `op` , como `op(t, u)` es equivalente a `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo del primer argumento de una función currificada.
### <a name="u"></a>' U

Tipo del segundo argumento de una función currificada.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)