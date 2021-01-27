---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833300"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray función)

Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Genera una representación binaria de un entero no negativo, utilizando la representación Little-Endian de la matriz devuelta.

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>Entrada

### <a name="number--int"></a>número: [int](xref:microsoft.quantum.lang-ref.int)

Entero no negativo que se va a convertir en una matriz de valores booleanos.


### <a name="bits--int"></a>bits: [int](xref:microsoft.quantum.lang-ref.int)

Número de bits en la representación binaria de `number` .



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Matriz de valores booleanos que representan `number` .

## <a name="remarks"></a>Observaciones

La entrada `bits` debe estar comprendida entre 0 y 63.
La entrada `number` debe estar comprendida entre 0 y $2 ^ {\texttt{bits}}-$1.