---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: f3e5ecf3f7df0393dfbb948f064c27505f04cfcf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728289"
---
# <a name="uncurriedopc-function"></a>UncurriedOpC función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Dada una función que devuelve operaciones, devuelve una nueva operación que toma ambas entradas como una tupla.
El modificador `C` indica que las operaciones se pueden controlar.

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a>Entrada

### <a name="curriedop--t---u--unit-ctl"></a>curriedOp: ' U = > ' U => de la [unidad](xref:microsoft.quantum.lang-ref.unit) CTL

Función que devuelve las operaciones.



## <a name="output--tu--unit-ctl"></a>Salida: (' t, ' U) => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)

Una nueva operación `op` , como `op(t, u)` es equivalente a `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo del primer argumento de una función currificada.
### <a name="u"></a>' U

Tipo del segundo argumento de una función currificada.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)