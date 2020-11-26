---
uid: Microsoft.Quantum.Arrays.Mapped
title: Función asignada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 9632b9f53ffad8ece958ab1dc9ad446c7dcb9e13
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220746"
---
# <a name="mapped-function"></a>Función asignada

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una matriz y una función que se define para los elementos de la matriz, devuelve una nueva matriz que consta de las imágenes de la matriz original en la función.

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Entrada

### <a name="mapper--t---u"></a>Mapper: ' t-> ' U

Función de `'T` a `'U` que se usa para asignar elementos.


### <a name="array--t"></a>matriz: ' t []

Matriz de elementos sobre `'T` .



## <a name="output--u"></a>Salida: ' U []

Matriz `'U[]` de elementos que se asignan mediante la `mapper` función.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de `array` elementos.
### <a name="u"></a>' U

El tipo de resultado de la `mapper` función.

## <a name="remarks"></a>Observaciones

La función se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y una función, `mapper: 'T -> 'U` podemos asignar los elementos de la matriz y generar una nueva matriz de tipo `'U[]` .