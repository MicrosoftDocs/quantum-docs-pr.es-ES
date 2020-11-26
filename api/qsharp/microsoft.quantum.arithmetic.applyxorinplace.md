---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: Operación ApplyXorInPlace
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: b7fc20ac421d5cff9baa3fe05450c1564f123505
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210120"
---
# <a name="applyxorinplace-operation"></a>Operación ApplyXorInPlace

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una operación XOR bit a bit entre un entero clásico y un entero representado por un registro de qubits.

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descripción

Aplica `X` operaciones a qubits en un registro Little-Endian basado en 1 bit en un entero.

Vamos `value` a indicar mediante un y dejar que y sea un entero sin signo codificado en `target` , `InPlaceXorLE` realiza una operación proporcionada por la siguiente asignación: $ \ket{y}\rightarrow \ket{y\oplus a} $, donde $ \oplus $ es el operador OR exclusivo bit a bit.

## <a name="input"></a>Entrada

### <a name="value--int"></a>valor: [int](xref:microsoft.quantum.lang-ref.int)

Entero que se supone que no es negativo.


### <a name="target--littleendian"></a>destino: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Un registro de Quantum que se usa para almacenar `value` en la codificación Little-Endian.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)

