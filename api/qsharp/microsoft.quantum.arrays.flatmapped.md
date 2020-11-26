---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: e851e8503b3afcb4572f09fe39079247518c22c4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221256"
---
# <a name="flatmapped-function"></a>FlatMapped función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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