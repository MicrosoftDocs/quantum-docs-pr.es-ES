---
uid: Microsoft.Quantum.Arrays.DrawMany
title: Operación DrawMany
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 3185f2ec01a2b9d01cff82a0c4667f12483801a7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210002"
---
# <a name="drawmany-operation"></a>Operación DrawMany

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Repite una operación para un número determinado de muestras, recopilando sus resultados en una matriz.

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a>Entrada

### <a name="op--tinput--toutput"></a>OP: ' TInput => ' TOutput ' 

Operación a la que se va a llamar varias veces.


### <a name="nsamples--int"></a>nSamples: [int](xref:microsoft.quantum.lang-ref.int)

Número de muestras de la llamada `op` a que se va a recopilar.


### <a name="input--tinput"></a>entrada: ' TInput

Entrada que se va a pasar a `op` .



## <a name="output--toutput"></a>Salida: ' TOutput []



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="tinput"></a>' TInput


### <a name="toutput"></a>' TOutput '



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. REPEAT](xref:Microsoft.Quantum.Canon.Repeat)