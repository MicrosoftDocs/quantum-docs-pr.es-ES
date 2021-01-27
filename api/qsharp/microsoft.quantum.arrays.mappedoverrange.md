---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: 7093043e2a290e6132774b8fe154d3627a254f27
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845650"
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

## <a name="example"></a>Ejemplo

En este ejemplo se suma 1 a un intervalo de números pares:

```qsharp
let numbers = MappedOverRange(PlusI(1, _), 0..2..10);
// numbers = [1, 3, 5, 7, 9, 11]
```

## <a name="remarks"></a>Observaciones

La función se define para tipos genéricos, es decir, cada vez que se tiene una función, `mapper: Int -> 'T` se pueden asignar los valores del intervalo y generar una matriz de tipo `'T[]` .

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. arrays. alpped](xref:Microsoft.Quantum.Arrays.Mapped)