---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: Operación ApplyXorInPlace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 5a35abc16a967e64c84466a47844ed7beeb618dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731700"
---
# <a name="applyxorinplace-operation"></a>Operación ApplyXorInPlace

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Configura [](https://nuget.org/packages/)


Aplica una operación XOR bit a bit entre un entero clásico y un entero representado por un registro de qubits.

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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

