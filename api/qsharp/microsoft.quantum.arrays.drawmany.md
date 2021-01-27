---
uid: Microsoft.Quantum.Arrays.DrawMany
title: Operación DrawMany
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: bf63ce308679cef97c776d3383ff732ed4d4e500
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846200"
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



## <a name="example"></a>Ejemplo

En los siguientes ejemplos se muestra un entero, dada una operación que muestrea un solo bit cada vez.

```qsharp
let randomInteger = BoolArrayAsInt(DrawMany(SampleRandomBit, 16, ()));
```

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. REPEAT](xref:Microsoft.Quantum.Canon.Repeat)