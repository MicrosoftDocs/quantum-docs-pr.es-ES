---
uid: Microsoft.Quantum.Arrays.Sorted
title: Función ordenada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: cb8a1ef438d798c8201ed9f52677e253770df1d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845440"
---
# <a name="sorted-function"></a>Función ordenada

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una matriz, devuelve los elementos de esa matriz ordenados por una función de comparación determinada.

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="comparison--tt---bool"></a>comparación: (' t, ')-> [bool](xref:microsoft.quantum.lang-ref.bool)

Función que compara dos elementos que `a` se considera que son menores o iguales que `b` si `comparison(a, b)` es `true` .


### <a name="array--t"></a>matriz: ' t []

Matriz que se va a ordenar.



## <a name="output--t"></a>Salida: ' t []



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de cada elemento de `array` .

## <a name="example"></a>Ejemplo

El siguiente fragmento de código ordena una matriz de enteros para que se produzca en orden ascendente:

```qsharp
let sortedArray = Sorted(LessThanOrEqualI, [3, 17, 11, -201, -11]);
```

## <a name="remarks"></a>Observaciones

Se supone que la función `comparison` es transitiva, de modo que si `comparison(a, b)` y `comparison(b, c)` , `comparison(a, c)` se supone. Si esta propiedad no contiene, la salida de esta función puede ser incorrecta.

Como es una función, los resultados son completamente determinstic, incluso cuando dos elementos se consideran iguales en `comparison` ; es decir, cuando `comparison(a, b)` y `comparison(b, a)` son ambos `true` .
En concreto, se garantiza que la ordenación realizada por esta función es estable, de modo que si dos elementos `a` y `b` se producen en ese orden en `array` y se consideran iguales en `comparison` , `a` también aparecerán antes `b` en la salida.

Por ejemplo:

```qsharp
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```