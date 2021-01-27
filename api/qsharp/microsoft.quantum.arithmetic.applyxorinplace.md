---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: Operación ApplyXorInPlace
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 8f338d6638d554f3ead1f3c0e7b6605c7937abd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843466"
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

