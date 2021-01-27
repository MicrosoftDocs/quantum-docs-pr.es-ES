---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 910d8a3006a2f217888b791e479e10f9f1a6965e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840035"
---
# <a name="uncurriedopca-function"></a>UncurriedOpCA función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una función que devuelve operaciones, devuelve una nueva operación que toma ambas entradas como una tupla.
El modificador `CA` indica que las operaciones se pueden controlar y adjointable.

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a>Entrada

### <a name="curriedop--t---u--unit--is-adj--ctl"></a>curriedOp: ' U = la [unidad](xref:microsoft.quantum.lang-ref.unit)  > de> es ADJ + CTL

Función que devuelve las operaciones.



## <a name="output--tu--unit--is-adj--ctl"></a>Output: (' t, ' U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL

Una nueva operación `op` , como `op(t, u)` es equivalente a `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo del primer argumento de una función currificada.
### <a name="u"></a>' U

Tipo del segundo argumento de una función currificada.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)