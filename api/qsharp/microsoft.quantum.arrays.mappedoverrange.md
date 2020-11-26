---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: b1d73c2503e63ed09a3d6a56421760ca29eb0c3f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220695"
---
# <a name="mappedoverrange-function"></a>MappedOverRange función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dado un intervalo y una función que toma un entero como entrada, devuelve una nueva matriz que consta de las imágenes de los valores de intervalo de la función.

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="mapper--int---t"></a>asignador: [int](xref:microsoft.quantum.lang-ref.int) -> ' t

Función de `Int` a `'T` que se utiliza para asignar valores de intervalo.


### <a name="range--range"></a>intervalo: [intervalo](xref:microsoft.quantum.lang-ref.range)

Un intervalo de enteros.



## <a name="output--t"></a>Salida: ' t []

Matriz `'T[]` de elementos que se asignan mediante la `mapper` función.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

El tipo de resultado de la `mapper` función.

## <a name="remarks"></a>Observaciones

La función se define para tipos genéricos, es decir, cada vez que se tiene una función, `mapper: Int -> 'T` se pueden asignar los valores del intervalo y generar una matriz de tipo `'T[]` .

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. arrays. alpped](xref:Microsoft.Quantum.Arrays.Mapped)