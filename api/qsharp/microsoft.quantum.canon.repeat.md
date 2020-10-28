---
uid: Microsoft.Quantum.Canon.Repeat
title: Repetir operación
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5aedd056b851b8d8d7c25a32eb22587292e132a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728456"
---
# <a name="repeat-operation"></a>Repetir operación

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Repite una operación un número determinado de veces.

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a>Entrada

### <a name="op--tinput--unit"></a>OP: ' TInput => [unidad](xref:microsoft.quantum.lang-ref.unit) 

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
- [Microsoft. Quantum. Canon. Repeata](xref:Microsoft.Quantum.Canon.RepeatA)
- [Microsoft. Quantum. Canon. RepeatC](xref:Microsoft.Quantum.Canon.RepeatC)
- [Microsoft. Quantum. Canon. RepeatCA](xref:Microsoft.Quantum.Canon.RepeatCA)