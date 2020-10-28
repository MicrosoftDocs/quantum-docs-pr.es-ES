---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: 21df20354ad2388891f32b1bf1c7781287904983
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728294"
---
# <a name="uncurriedopa-function"></a>UncurriedOpA función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Dada una función que devuelve operaciones, devuelve una nueva operación que toma ambas entradas como una tupla.
El modificador `A` indica que las operaciones son adjointable.

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a>Entrada

### <a name="curriedop--t---u--unit-adj"></a>curriedOp: ' U = > ' U => de [unidad](xref:microsoft.quantum.lang-ref.unit)

Función que devuelve las operaciones.



## <a name="output--tu--unit-adj"></a>Salida: (' t, ' U) => de [unidad](xref:microsoft.quantum.lang-ref.unit)

Una nueva operación `op` , como `op(t, u)` es equivalente a `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo del primer argumento de una función currificada.
### <a name="u"></a>' U

Tipo del segundo argumento de una función currificada.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)