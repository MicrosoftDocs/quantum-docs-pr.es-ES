---
uid: Microsoft.Quantum.Canon.ConjugatedByA
title: ConjugatedByA función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: bcaab28e99d3d61f4a36da866321d28f3dc4bd53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728828"
---
# <a name="conjugatedbya-function"></a>ConjugatedByA función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Dadas las operaciones externas e internas, devuelve una nueva operación que conjuga la operación interna mediante la operación externa.

```qsharp
function ConjugatedByA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj)) : ('T => Unit is Adj)
```


## <a name="input"></a>Entrada

### <a name="outeroperation--t--unit-adj"></a>outerOperation: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)

La operación $U $ que se debe usar para conjugado $V $. Tenga en cuenta que la operación exterior $U $ debe ser adjointable, pero no es necesario que sea controlable.


### <a name="inneroperation--t--unit-adj"></a>innerOperation: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)

Operación $V $ que se va a conjugado.



## <a name="output--t--unit-adj"></a>Salida: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)

Nueva operación cuya acción está representada por la unidad de $U ^ {\dagger} V U $.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo del destino en el que actúa cada una de las operaciones internas y externas.

## <a name="remarks"></a>Observaciones

La operación exterior siempre se supone que es adjointable, pero no es necesario que se pueda controlar para que la operación combinada sea controlable.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ConjugatedByA](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [Microsoft. Quantum. Canon. ConjugatedByC](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [Microsoft. Quantum. Canon. ConjugatedByCA](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [Microsoft. Quantum. Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)