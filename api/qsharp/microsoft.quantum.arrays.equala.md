---
uid: Microsoft.Quantum.Arrays.EqualA
title: Equala (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 24fd76aaeb66081d6d8f1eaa3056117f54b5a5e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730293"
---
# <a name="equala-function"></a>Equala (función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Configura [](https://nuget.org/packages/)


Dadas dos matrices del mismo tipo y un predicado definido para pares de elementos de las matrices, comprueba si las matrices son iguales.

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a>Entrada

### <a name="equal--tt---bool"></a>igual: (' t, ')-> [bool](xref:microsoft.quantum.lang-ref.bool)

Función de Tuple `('T, 'T)` a `Bool` que se usa para comprobar si dos elementos de matrices son iguales.


### <a name="array1--t"></a>matriz1: ' t []

Primera matriz que se va a comparar.


### <a name="array2--t"></a>matriz2: ' t []

Segunda matriz que se va a comparar.



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

Valor `true` si y solo si `array1` y `array2` son iguales.
Es decir, si ambas matrices tienen la misma longitud y todos los elementos son iguales que los definidos por `equal` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de los elementos de cada matriz.

## <a name="remarks"></a>Observaciones

Esta función se define para tipos genéricos; es decir, cada vez que tenemos dos matrices `'T[]` y una función `equal: ('T, 'T) -> Bool` , esta función devuelve un `Bool` valor que indica si las matrices son iguales.
Para que dos matrices se consideren iguales, deben tener la misma longitud y los elementos de las mismas posiciones en las matrices deben ser iguales.