---
uid: Microsoft.Quantum.Arrays.Unique
title: Función Unique
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: b3aa03d20195bdd8bb64783a9b68cafac29e68f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850925"
---
# <a name="unique-function"></a>Función Unique

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve una nueva matriz que no tiene elementos adyacentes iguales.

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a>Descripción

Dada una matriz de elementos y una función para probar la igualdad, esta función devuelve una nueva matriz en la que se conserva el orden relativo de los elementos, pero todos los elementos adyacentes que son iguales se filtran por un solo elemento.

## <a name="input"></a>Entrada

### <a name="equal--tt---bool"></a>igual: (' t, ')-> [bool](xref:microsoft.quantum.lang-ref.bool)

Función que compara dos elementos que `a` se considera que son iguales que `b` si `equal(a, b)` es `true` .


### <a name="array--t"></a>matriz: ' t []

Matriz que se va a filtrar para los elementos únicos.



## <a name="output--t"></a>Salida: ' t []

Matriz sin elementos adyacentes iguales.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de cada elemento de `array` .

## <a name="example"></a>Ejemplo

```qsharp
let unique1 = Unique(EqualI, [1, 1, 3, 3, 2, 5, 5, 5, 7]);
// same as [1, 3, 2, 5, 7]
let unique2 = Unique(EqualI, [2, 2, 1, 1, 2, 2, 1, 1]);
// same as [2, 1, 2, 1];
let unique3 = Unique(EqualI, Sorted(LessThanOrEqualI, [2, 2, 1, 1, 2, 2, 1, 1]));
// same as [1, 2];
```

## <a name="remarks"></a>Observaciones

Si hay varios elementos que son iguales pero no próximos entre sí, habrá varias repeticiones en la matriz de salida.  Use esta función junto con `Sorted` para obtener una matriz con elementos únicos generales.