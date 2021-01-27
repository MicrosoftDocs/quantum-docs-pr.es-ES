---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Operación ApplyControlledOnInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 499a25104742b2d03886065baad4d535ea92e83b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845096"
---
# <a name="applycontrolledonint-operation"></a>Operación ApplyControlledOnInt

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una operación de unitario en el registro de destino si el estado del registro de control corresponde a un entero positivo especificado.

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="numberstate--int"></a>numberState: [int](xref:microsoft.quantum.lang-ref.int)

Entero no negativo en el que `oracle` se debe controlar la operación.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL

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