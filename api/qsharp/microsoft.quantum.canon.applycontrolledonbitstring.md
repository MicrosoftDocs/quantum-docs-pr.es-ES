---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Operación ApplyControlledOnBitString
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 82adc74e23e1d50cb6436176a973fdd1a0eeb3bd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841938"
---
# <a name="applycontrolledonbitstring-operation"></a>Operación ApplyControlledOnBitString

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una operación de unitario en el registro de destino, controlada en un estado especificado por una máscara de bits determinada.

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="bits--bool"></a>bits: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Cadena de bits en la que se va a controlar la operación de unitario especificada.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL

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