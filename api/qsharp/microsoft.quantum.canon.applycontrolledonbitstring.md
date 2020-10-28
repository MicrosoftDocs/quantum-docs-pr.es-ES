---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Operación ApplyControlledOnBitString
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 7a054511bacff574e6f7e889ace048c78886cf91
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729676"
---
# <a name="applycontrolledonbitstring-operation"></a>Operación ApplyControlledOnBitString

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica una operación de unitario en el registro de destino, controlada en un estado especificado por una máscara de bits determinada.

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a>Entrada

### <a name="bits--bool"></a>bits: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Cadena de bits en la que se va a controlar la operación de unitario especificada.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL

La operación unitario que se va a aplicar al registro de destino.


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registro Quantum que controla la aplicación de `oracle` .


### <a name="targetregister--t"></a>targetRegister: ' t

Registro de destino que se va a pasar a `oracle` como entrada.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada



## <a name="remarks"></a>Observaciones

El patrón proporcionado por `bits` puede ser más corto que `controlRegister` , en cuyo caso se omiten los qubits de control adicionales (es decir, no se controlan en $ \ket {0} $ ni $ \ket {1} $).
Si `bits` es mayor que `controlRegister` , se genera un error.

Por ejemplo, `bits = [0,1,0,0,1]` significa que `oracle` se aplica si y solo si `controlRegister` está en el estado $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $.