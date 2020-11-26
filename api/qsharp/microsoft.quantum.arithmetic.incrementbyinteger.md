---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: Operación IncrementByInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fa5e75e91206aa5f33233c8a54d6e9e7ac2950e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222973"
---
# <a name="incrementbyinteger-operation"></a>Operación IncrementByInteger

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Incrementa un registro de Quantum sin signo mediante un entero clásico, usando giros de fase.

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descripción

Supongamos que `target` codifica un entero sin signo $x $ en una codificación Little-endian y que `increment` es igual a $a $.
A continuación, esta operación implementa la unitario $ \ket{x} \mapsto \ket{x + a} $, donde la adición se realiza en módulo $2 ^ n $, donde $n = \texttt{Length (Target!)} $.

## <a name="input"></a>Entrada

### <a name="increment--int"></a>incremento: [int](xref:microsoft.quantum.lang-ref.int)

Entero por el que `target` se incrementa.


### <a name="target--littleendian"></a>destino: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Un registro de Quantum codifica un entero sin signo mediante la codificación Little-Endian.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)

