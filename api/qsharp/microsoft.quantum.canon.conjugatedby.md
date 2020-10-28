---
uid: Microsoft.Quantum.Canon.ConjugatedBy
title: ConjugatedBy función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedBy
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 37fbee9a7c11991645933a372f9f12c1fd696b66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728829"
---
# <a name="conjugatedby-function"></a>ConjugatedBy función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Dadas las operaciones externas e internas, devuelve una nueva operación que conjuga la operación interna mediante la operación externa.

```qsharp
function ConjugatedBy<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit)) : ('T => Unit)
```


## <a name="input"></a>Entrada

### <a name="outeroperation--t--unit-adj"></a>outerOperation: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)

La operación $U $ que se debe usar para conjugado $V $. Tenga en cuenta que la operación exterior $U $ debe ser adjointable, pero no es necesario que sea controlable.


### <a name="inneroperation--t--unit"></a>innerOperation: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Operación $V $ que se va a conjugado.



## <a name="output--t--unit"></a>Salida: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de> 

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