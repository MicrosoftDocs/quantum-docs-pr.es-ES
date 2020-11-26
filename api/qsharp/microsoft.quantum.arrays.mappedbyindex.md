---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 430495517974b641c249fa146aa9effec542e825
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209934"
---
# <a name="mappedbyindex-function"></a>MappedByIndex función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una matriz y una función que se define para los elementos indizados de la matriz, devuelve una nueva matriz que consta de las imágenes de la matriz original en la función.

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Entrada

### <a name="mapper--intt---u"></a>asignador: ([int](xref:microsoft.quantum.lang-ref.int), ' t)-> ' U

Función de `(Int, 'T)` a `'U` que se usa para asignar elementos y sus índices.


### <a name="array--t"></a>matriz: ' t []

Matriz de elementos sobre `'T` .



## <a name="output--u"></a>Salida: ' U []

Matriz `'U[]` de elementos que se asignan mediante la `mapper` función.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de `array` elementos.
### <a name="u"></a>' U

El tipo de resultado de la `mapper` función.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. arrays. alpped](xref:Microsoft.Quantum.Arrays.Mapped)