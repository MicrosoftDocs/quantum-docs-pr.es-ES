---
uid: Microsoft.Quantum.Arrays.IsSorted
title: IsSorted (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: b2c5f11c0d92ddf9214de2d439c175319c569be0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220843"
---
# <a name="issorted-function"></a>IsSorted (función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una matriz, devuelve si esa matriz se ordena según lo definido por una función de comparación determinada.

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Entrada

### <a name="comparison--tt---bool"></a>comparación: (' t, ')-> [bool](xref:microsoft.quantum.lang-ref.bool)

Función que compara dos elementos que `a` se considera que son menores o iguales que `b` si `comparison(a, b)` es `true` .


### <a name="array--t"></a>matriz: ' t []

Matriz que se va a comprobar.



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si y solo si para cada par de elementos `a` y `b` `array` se producen en ese orden, `comparison(a, b)` es `true` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de cada elemento de `array` .

## <a name="remarks"></a>Observaciones

Se supone que la función `comparison` es transitiva, de modo que si `comparison(a, b)` y `comparison(b, c)` , `comparison(a, c)` se supone. Si esta propiedad no contiene, la salida de esta función puede ser incorrecta.