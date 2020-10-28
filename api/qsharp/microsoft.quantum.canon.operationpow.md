---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 5cf9017175f44a8a0b8f865624a6c312d25aded1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728529"
---
# <a name="operationpow-function"></a>OperationPow función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Eleva una operación a una potencia.

Es decir, dada una operación que representa una puerta $U $, devuelve una nueva operación $U ^ m $ para una potencia $m $.

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit"></a>OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de> 

Operación $U $ que representa la puerta que se va a repetir.


### <a name="power--int"></a>potencia: [int](xref:microsoft.quantum.lang-ref.int)

Número de veces que se va a repetir el $U $.



## <a name="output--t--unit"></a>Salida: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de> 

Nueva operación que representa $U ^ m $, donde $m = \texttt{Power} $.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de la operación que se va a alimentar.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. OperationPowC](xref:Microsoft.Quantum.Canon.OperationPowC)
- [Microsoft. Quantum. Canon. OperationPowA](xref:Microsoft.Quantum.Canon.OperationPowA)
- [Microsoft. Quantum. Canon. OperationPowCA](xref:Microsoft.Quantum.Canon.OperationPowCA)