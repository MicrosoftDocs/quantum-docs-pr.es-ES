---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 176170cc972ca67b812b84f79cf97ba5418be9b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840797"
---
# <a name="controlledonbitstring-function"></a>ControlledOnBitString función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve una operación de unitario que aplica un Oracle en el registro de destino si el estado del registro de control corresponde a una máscara de bits especificada.

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a>Descripción

La salida de esta función es una operación que se puede representar mediante una transformación unitario $U $ como \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{bits} \\ \\ \ket{\psi} & \textrm{otherwise} \end{Cases}, \end{align} donde $V $ es una transformación de unitario que representa la acción de la `oracle` operación.

## <a name="input"></a>Entrada

### <a name="bits--bool"></a>bits: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Cadena de bits en la que se va a controlar la operación de unitario especificada.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL

La operación unitario que se va a aplicar al registro de destino.



## <a name="output--qubitt--unit--is-adj--ctl"></a>Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], ' t) => [Unit](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL

Operación de unitario que se aplica `oracle` en el registro de destino si el estado del registro de control corresponde a la máscara de bits `bits` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada



## <a name="example"></a>Ejemplo

Los siguientes fragmentos de código son equivalentes:

```qsharp
(ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
```

y

```qsharp
within {
    ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
} apply {
    Controlled oracle(controlRegister, targetRegister);
}
```

En el código siguiente se prepara un estado $ \frac {1} {2} (\ket {00} -\ket {01} + \ket {10} + \ket {11} ) $:

```qsharp
using (register = Qubit[2]) {
    ApplyToEach(H, register);
    (ControlledOnBitString([false], Z))(register[0..0], register[1]);
}
```

## <a name="remarks"></a>Observaciones

El patrón proporcionado por `bits` puede ser más corto que `controlRegister` , en cuyo caso se omiten los qubits de control adicionales (es decir, no se controlan en $ \ket {0} $ ni $ \ket {1} $).
Si `bits` es mayor que `controlRegister` , se genera un error.

Dada una matriz booleana `bits` y una operación unitario `oracle` , la salida de esta función es una operación que realiza los pasos siguientes:

* Aplique una `X` operación a cada qubit del registro de control que se corresponda con `false` el elemento de `bits` ;
* se aplican `Controlled oracle` a los registros de control y de destino;
* Aplique una `X` operación a cada qubit del registro de control que se corresponda con el `false` elemento de de `bits` nuevo para devolver el registro de control al estado original.

La salida del `Controlled` functor es un caso especial de `ControlledOnBitString` donde `bits` es igual a `[true, ..., true]` .