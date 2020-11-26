---
uid: Microsoft.Quantum.Arrays.Excluding
title: Exclusión de función
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 6585e619834a96953c9eae2d36a8ebe0a11dbda0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221324"
---
# <a name="excluding-function"></a>Exclusión de función

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve una matriz que contiene los elementos de otra matriz, excluidos los elementos de una lista determinada de índices.

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="remove--int"></a>quitar: [int](xref:microsoft.quantum.lang-ref.int)[]

Matriz de índices que indican qué elementos se deben excluir de la salida.


### <a name="array--t"></a>matriz: ' t []

Matriz de la que se toman los valores de la matriz de salida.



## <a name="output--t"></a>Salida: ' t []

Matriz de `output` tipo que `output[0]` es el primer elemento de `array` cuyo índice no aparece en `remove` , tal que `output[1]` es el segundo elemento de este tipo, y así sucesivamente.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

El tipo de los elementos de la matriz.