---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: 359c0b2a9dd56445fb39fadc6580809dd9fbf628
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728301"
---
# <a name="uncurriedop-function"></a>UncurriedOp función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Dada una función que devuelve operaciones, devuelve una nueva operación que toma ambas entradas como una tupla.

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a>Entrada

### <a name="curriedop--t---u--unit"></a>curriedOp: ' U = [unidad](xref:microsoft.quantum.lang-ref.unit) > de> 

Función que devuelve las operaciones.



## <a name="output--tu--unit"></a>Salida: (' t, ' U) = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Una nueva operación `op` , como `op(t, u)` es equivalente a `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

El tipo de la primera entrada a una operación currificada.
### <a name="u"></a>' U

Tipo de la segunda entrada a una operación currificada.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. UncurriedOpC](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [Microsoft. Quantum. Canon. UncurriedOpA](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [Microsoft. Quantum. Canon. UncurriedOpCA](xref:Microsoft.Quantum.Canon.UncurriedOpCA)