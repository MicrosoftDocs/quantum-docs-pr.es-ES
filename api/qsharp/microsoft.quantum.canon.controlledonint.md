---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 4c48f3257f91fc50040d02cae7c2f7bdf87ea7c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728805"
---
# <a name="controlledonint-function"></a>ControlledOnInt función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Devuelve un operador unitario que aplica un Oracle en el registro de destino si el estado del registro de control corresponde a un entero positivo especificado.

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="numberstate--int"></a>numberState: [int](xref:microsoft.quantum.lang-ref.int)

Entero positivo.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL

Operador unitario.



## <a name="output--qubitt--unit-adj--ctl"></a>Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], ' no) => [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL + CTL

Operador unitario que se aplica `oracle` en el registro de destino si el estado del registro de control corresponde al estado del número `numberState` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada



## <a name="remarks"></a>Observaciones

El valor de `numberState` se interpreta utilizando una codificación Little-Endian.