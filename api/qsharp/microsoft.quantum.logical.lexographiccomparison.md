---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: f0b68974a0ea26907b58971e4fa4b1f06f5714d2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726015"
---
# <a name="lexographiccomparison-function"></a>LexographicComparison función)

Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Configura [](https://nuget.org/packages/)


Dada una función de comparación, devuelve una nueva función que lexographically compara dos matrices.

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a>Entrada

### <a name="elementcomparison--tt---bool"></a>elementComparison: (' t, ' t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Función que compara dos elementos `x` y `y` y devuelve si `x` es menor o igual que `y` .



## <a name="output--tt---bool"></a>Salida: (' t [], ' t [])-> [bool](xref:microsoft.quantum.lang-ref.bool)

Función que compara dos matrices `xs` y `ys` y devuelve si `xs` se produce antes o igual que en el `ys` orden de lexographical.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de los elementos de las matrices que se van a comparar.

## <a name="remarks"></a>Observaciones

La comparación de lexographic entre dos matrices `xs` y `ys` se define mediante el procedimiento siguiente. Indicamos que dos elementos `x` y `y` son equivalentes si `elementComparison(x, y)` y `elementComparison(y, x)` son true.

- Ambas matrices se comparan elemento a elemento hasta el primer par de elementos que no son equivalentes. La matriz que contiene el elemento que se produce primero según `elementComparison` se dice que se produce primero en el orden de lexographical.
- Si no se encuentra ningún elemento no equivalente y una matriz es más larga que la otra, se dice que la matriz más corta se produce primero.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. matrices. Sorted](xref:Microsoft.Quantum.Arrays.Sorted)