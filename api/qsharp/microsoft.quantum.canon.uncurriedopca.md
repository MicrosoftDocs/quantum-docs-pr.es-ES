---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 6a0f2e1b345d0ba3ac5c779c5dc2bfffaf659a0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728288"
---
# <a name="uncurriedopca-function"></a>UncurriedOpCA función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Dada una función que devuelve operaciones, devuelve una nueva operación que toma ambas entradas como una tupla.
El modificador `CA` indica que las operaciones se pueden controlar y adjointable.

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a>Entrada

### <a name="curriedop--t---u--unit-ctl--adj"></a>curriedOp: ' t-> ' U => [unidad](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ

Función que devuelve las operaciones.



## <a name="output--tu--unit-ctl--adj"></a>Salida: (' t, ' U) = [unidad](xref:microsoft.quantum.lang-ref.unit) de> CTL + ADJ

Una nueva operación `op` , como `op(t, u)` es equivalente a `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo del primer argumento de una función currificada.
### <a name="u"></a>' U

Tipo del segundo argumento de una función currificada.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)