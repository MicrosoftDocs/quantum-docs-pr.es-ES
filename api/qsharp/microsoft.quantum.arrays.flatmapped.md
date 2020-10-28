---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: 3e75c7703471a2986812df660c2f9328f1536d22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730269"
---
# <a name="flatmapped-function"></a>FlatMapped función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Configura [](https://nuget.org/packages/)


Dada una matriz y una función que asigna un elemento de matriz a alguna matriz de salida, devuelve las matrices de salida concatenadas para cada elemento de la matriz.

```qsharp
function FlatMapped<'TInput, 'TOutput> (mapper : ('TInput -> 'TOutput[]), array : 'TInput[]) : 'TOutput[]
```


## <a name="input"></a>Entrada

### <a name="mapper--tinput---toutput"></a>asignador: ' TInput-> ' TOutput []

Función de `'TInput` a `'TOutput[]` que se usa para asignar elementos de matriz.


### <a name="array--tinput"></a>matriz: ' TInput []

Matriz de elementos.



## <a name="output--toutput"></a>Salida: ' TOutput []

Matriz de `'TOutput[]` la que es la concatenación de todas las matrices generadas por la función de asignación.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="tinput"></a>' TInput

Tipo de `array` elementos.
### <a name="toutput"></a>' TOutput '

La `mapper` función devuelve matrices de este tipo.