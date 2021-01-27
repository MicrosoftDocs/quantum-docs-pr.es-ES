---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: bee7002c5a1e80cee7907ff9cb4ebaaedf8e9923
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848636"
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

## <a name="example"></a>Ejemplo

```qsharp
let Numbers = SequenceI(1, _); // generates numbers starting from 1
let values = FlatMapped(Numbers, [1, 2, 3]);
// values = [1, 1, 2, 1, 2, 3]
```