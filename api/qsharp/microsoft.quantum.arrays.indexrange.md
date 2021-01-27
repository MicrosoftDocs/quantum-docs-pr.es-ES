---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845775"
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

## <a name="example"></a>Ejemplo

Los `for` bucles siguientes son equivalentes:

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```