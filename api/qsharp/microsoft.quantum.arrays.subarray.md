---
uid: Microsoft.Quantum.Arrays.Subarray
title: Subarray (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: ccc041da0213d1f5dc5c8b4ff7a03b8b01ad107d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845430"
---
# <a name="subarray-function"></a>Subarray (función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Toma una matriz y una lista de ubicaciones y genera una nueva matriz formada a partir de los elementos de la matriz original que coinciden con las ubicaciones especificadas.

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="indices--int"></a>índices: [int](xref:microsoft.quantum.lang-ref.int)[]

Una lista de enteros que se utiliza para definir la submatriz.


### <a name="array--t"></a>matriz: ' t []

Matriz de elementos sobre `'T` .



## <a name="output--t"></a>Salida: ' t []

Matriz `out` de elementos cuyos índices corresponden a la submatriz, de modo que `out[idx] == array[indices[idx]]` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de `array` elementos.

## <a name="remarks"></a>Observaciones

La función se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y una lista de ubicaciones que `Int[]` definen la submatriz.
La construcción de la submatriz es un basado en la generación de una nueva copia en profundidad de la matriz determinada en lugar de mantener referencias.

Si es `Length(indices) < Length(array)` , esta función devolverá un subconjunto de `array` . Por otro lado, si `indices` contiene elementos repetidos, los elementos correspondientes de también `array` se repetirán.
Si `indices` y `array` tienen la misma longitud, esta función proporciona permutaciones de `array` .