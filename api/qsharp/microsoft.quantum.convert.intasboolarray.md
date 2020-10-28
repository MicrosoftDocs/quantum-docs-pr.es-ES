---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727538"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray función)

Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Configura [](https://nuget.org/packages/)


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