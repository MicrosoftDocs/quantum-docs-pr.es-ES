---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Operación ApplyControlledOnInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729669"
---
# <a name="applycontrolledonint-operation"></a>Operación ApplyControlledOnInt

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica una operación de unitario en el registro de destino si el estado del registro de control corresponde a un entero positivo especificado.

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a>Entrada

### <a name="numberstate--int"></a>numberState: [int](xref:microsoft.quantum.lang-ref.int)

Entero no negativo en el que `oracle` se debe controlar la operación.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL

Operación de unitario que se va a controlar.


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registro Quantum que controla la aplicación de `oracle` .


### <a name="targetregister--t"></a>targetRegister: ' t

Registro en el que se va a aplicar `oracle` .



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada



## <a name="remarks"></a>Observaciones

El valor de `numberState` se interpreta utilizando una codificación Little-Endian.

`numberState` debe ser como máximo $2 ^ \texttt{Length (controlRegister)}-$1.
Por ejemplo, `numberState = 537` significa que `oracle` se aplica si y solo si `controlRegister` está en el estado $ \ket {537} $.