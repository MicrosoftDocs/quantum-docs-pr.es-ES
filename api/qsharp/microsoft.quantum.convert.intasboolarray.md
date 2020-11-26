---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: f89cb3d7ca29d7deaaf49573b2670534166caded
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224350"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray función)

Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Genera una representación binaria de un entero positivo, utilizando la representación Little-Endian de la matriz devuelta.

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>Entrada

### <a name="number--int"></a>número: [int](xref:microsoft.quantum.lang-ref.int)

Entero positivo que se va a convertir en una matriz de valores booleanos.


### <a name="bits--int"></a>bits: [int](xref:microsoft.quantum.lang-ref.int)

Número de bits en la representación binaria de `number` .



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Matriz de valores booleanos que representan `number` .

## <a name="remarks"></a>Observaciones

La entrada `bits` debe estar comprendida entre 0 y 63.
La entrada `number` debe estar comprendida entre 0 y $2 ^ {\texttt{bits}}-$1.