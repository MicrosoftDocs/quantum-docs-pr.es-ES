---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: Operación IncrementPhaseByInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 54b83b3d4460c05478543c51f8f9c0b0e7f5b1fa
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222922"
---
# <a name="incrementphasebyinteger-operation"></a>Operación IncrementPhaseByInteger

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Incrementa un registro de Quantum sin signo mediante un entero clásico, usando giros de fase.

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descripción

Supongamos que `target` codifica un entero sin signo $x $ en una codificación Little-endian y que `increment` es igual a $a $.
A continuación, esta operación implementa la unitario $ \ket{x} \mapsto \ket{x + a} $, donde la adición se realiza en módulo $2 ^ n $, donde $n = \texttt{Length (Target!)} $.

## <a name="input"></a>Entrada

### <a name="increment--int"></a>incremento: [int](xref:microsoft.quantum.lang-ref.int)

Entero por el que `target` se incrementa.


### <a name="target--phaselittleendian"></a>destino: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Un registro de Quantum codifica un entero sin signo mediante la codificación Little-endian en la base dual (QFT).



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Tenga en cuenta que se ha simplificado el circuito porque el incremento es una constante clásica, no un registro de Quantum.

Vea la ilustración de la [ Página 6 de arXiv: Quant-pH/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) para el diagrama del circuito y la explicación.

## <a name="references"></a>Referencias

- [*Thomas G. Draper*, arXiv: Quant-pH/0008033](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. aritmético. IncrementByInteger](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)