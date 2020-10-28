---
uid: Microsoft.Quantum.Canon.RepeatCA
title: Operación RepeatCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: b68c3aa4298fffa76f7c43ac4c6d27cdf3b72fbf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728433"
---
# <a name="repeatca-operation"></a>Operación RepeatCA

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Repite una operación un número determinado de veces.

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a>Entrada

### <a name="op--tinput--unit-adj--ctl"></a>OP: ' TInput => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL

Operación a la que se va a llamar varias veces.


### <a name="ntimes--int"></a>nTimes: [int](xref:microsoft.quantum.lang-ref.int)

Número de veces que se va a llamar a `op` .


### <a name="input--tinput"></a>entrada: ' TInput

Entrada que se va a pasar a `op` .



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="tinput"></a>' TInput



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. arrays. DrawMany](xref:Microsoft.Quantum.Arrays.DrawMany)
- [Microsoft. Quantum. Canon. REPEAT](xref:Microsoft.Quantum.Canon.Repeat)
- [Microsoft. Quantum. Canon. Repeata](xref:Microsoft.Quantum.Canon.RepeatA)
- [Microsoft. Quantum. Canon. RepeatC](xref:Microsoft.Quantum.Canon.RepeatC)