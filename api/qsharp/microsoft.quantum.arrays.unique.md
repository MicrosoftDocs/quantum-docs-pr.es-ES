---
uid: Microsoft.Quantum.Arrays.Unique
title: Función Unique
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: c5d40bb82f2de640e9c78eef0c27e4766b477826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729957"
---
# <a name="unique-function"></a>Función Unique

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Configura [](https://nuget.org/packages/)


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

## <a name="remarks"></a>Observaciones

Si hay varios elementos que son iguales pero no próximos entre sí, habrá varias repeticiones en la matriz de salida.  Use esta función junto con `Sorted` para obtener una matriz con elementos únicos generales.