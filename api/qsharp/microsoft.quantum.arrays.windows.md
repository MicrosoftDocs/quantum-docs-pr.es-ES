---
uid: Microsoft.Quantum.Arrays.Windows
title: Función de Windows
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: adfea2b9a2f6c22446817538d29586284dba723e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842190"
---
# <a name="windows-function"></a>Función de Windows

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Ejemplo

```qsharp
// same as [[1, 2, 3], [2, 3, 4], [3, 4, 5]]
let windows = Windows(3, [1, 2, 3, 4, 5]);
```