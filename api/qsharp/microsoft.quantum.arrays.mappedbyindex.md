---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845666"
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

## <a name="example"></a>Ejemplo

Las dos líneas siguientes son equivalentes:

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

y

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. arrays. alpped](xref:Microsoft.Quantum.Arrays.Mapped)