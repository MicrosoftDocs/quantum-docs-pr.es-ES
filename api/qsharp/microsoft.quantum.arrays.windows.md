---
uid: Microsoft.Quantum.Arrays.Windows
title: Función de Windows
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729933"
---
# <a name="windows-function"></a>Función de Windows

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Configura [](https://nuget.org/packages/)


Devuelve todas las submatrices consecutivas de longitud `size` .

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a>Descripción

Esta función devuelve todas las `n - size + 1` submatrices de longitud `size` en orden, donde `n` es la longitud de `arr` .
Las primeras submatrices son `arr[0..size - 1], arr[1..size], arr[2..size + 1]` hasta la última submatriz `arr[n - size..n - 1]` .

Si `size <= 0` o `size > n` es, se devuelve una matriz vacía.

## <a name="input"></a>Entrada

### <a name="size--int"></a>tamaño: [int](xref:microsoft.quantum.lang-ref.int)

Longitud de las submatrices.


### <a name="array--t"></a>matriz: ' t []

Matriz de elementos.



## <a name="output--t"></a>Salida: ' t [] []



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de `array` elementos.