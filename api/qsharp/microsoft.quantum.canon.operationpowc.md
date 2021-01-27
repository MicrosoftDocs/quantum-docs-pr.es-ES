---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 05b0d5b286e16c308d8c3df8fb8fa1ac8c9868ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852347"
---
# <a name="operationpowc-function"></a>OperationPowC función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Eleva una operación a una potencia.
El modificador `C` indica que la operación es controlable.

Es decir, dada una operación que representa una puerta $U $, devuelve una nueva operación $U ^ m $ para una potencia $m $.

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit--is-ctl"></a>OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL

Operación $U $ que representa la puerta que se va a repetir.


### <a name="power--int"></a>potencia: [int](xref:microsoft.quantum.lang-ref.int)

Número de veces que se va a repetir el $U $.



## <a name="output--t--unit--is-ctl"></a>Salida: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL

Nueva operación que representa $U ^ m $, donde $m = \texttt{Power} $.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de la operación que se va a alimentar.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)