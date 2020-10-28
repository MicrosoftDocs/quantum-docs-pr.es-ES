---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 753063452616747309e3e228ce8a702f4378c61f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728487"
---
# <a name="operationpowca-function"></a>OperationPowCA función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Eleva una operación a una potencia.
El modificador `A` indica que la operación es controlable y adjointable.

Es decir, dada una operación que representa una puerta $U $, devuelve una nueva operación $U ^ m $ para una potencia $m $.

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit-ctl--adj"></a>OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de> CTL + ADJ

Operación $U $ que representa la puerta que se va a repetir.


### <a name="power--int"></a>potencia: [int](xref:microsoft.quantum.lang-ref.int)

Número de veces que se va a repetir el $U $.



## <a name="output--t--unit-ctl--adj"></a>Salida: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de> CTL + ADJ

Nueva operación que representa $U ^ m $, donde $m = \texttt{Power} $.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de la operación que se va a alimentar.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)