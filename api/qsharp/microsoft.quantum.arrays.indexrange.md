---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 5afd4cc260ac3e384d2736bf7b43d941afd9ef73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220950"
---
# <a name="indexrange-function"></a>IndexRange función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Dada una matriz, devuelve un intervalo sobre los índices de esa matriz, adecuado para su uso en un bucle for.

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a>Entrada

### <a name="array--telement"></a>matriz: ' Telement []

Matriz para la que se debe devolver un intervalo de índices.



## <a name="output--range"></a>Salida: [intervalo](xref:microsoft.quantum.lang-ref.range)

Un intervalo de todos los índices de la matriz.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="telement"></a>' TEle

Tipo de elementos de la matriz.