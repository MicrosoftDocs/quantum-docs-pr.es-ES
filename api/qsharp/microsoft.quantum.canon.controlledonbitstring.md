---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: ca5a6e116eff187060f7a160e42836b170f0362d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728817"
---
# <a name="controlledonbitstring-function"></a>ControlledOnBitString función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Devuelve una operación de unitario que aplica un Oracle en el registro de destino si el estado del registro de control corresponde a una máscara de bits especificada.

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a>Descripción

La salida de esta función es una operación que se puede representar mediante una transformación unitario $U $ como \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{bits} \\ \\ \ket{\psi} & \textrm{otherwise} \end{Cases}, \end{align} donde $V $ es una transformación de unitario que representa la acción de la `oracle` operación.

## <a name="input"></a>Entrada

### <a name="bits--bool"></a>bits: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Cadena de bits en la que se va a controlar la operación de unitario especificada.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL

La operación unitario que se va a aplicar al registro de destino.



## <a name="output--qubitt--unit-adj--ctl"></a>Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], ' no) => [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL + CTL

Operación de unitario que se aplica `oracle` en el registro de destino si el estado del registro de control corresponde a la máscara de bits `bits` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada



## <a name="remarks"></a>Observaciones

El patrón proporcionado por `bits` puede ser más corto que `controlRegister` , en cuyo caso se omiten los qubits de control adicionales (es decir, no se controlan en $ \ket {0} $ ni $ \ket {1} $).
Si `bits` es mayor que `controlRegister` , se genera un error.

Dada una matriz booleana `bits` y una operación unitario `oracle` , la salida de esta función es una operación que realiza los pasos siguientes:

* Aplique una `X` operación a cada qubit del registro de control que se corresponda con `false` el elemento de `bits` ;
* se aplican `Controlled oracle` a los registros de control y de destino;
* Aplique una `X` operación a cada qubit del registro de control que se corresponda con el `false` elemento de de `bits` nuevo para devolver el registro de control al estado original.

La salida del `Controlled` functor es un caso especial de `ControlledOnBitString` donde `bits` es igual a `[true, ..., true]` .