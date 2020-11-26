---
uid: Microsoft.Quantum.Arrays.Count
title: Count, función
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 48b75cc6d6584f899223a0803f31fd174836f303
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221562"
---
# <a name="count-function"></a>Count, función

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una matriz y un predicado definidos para los elementos de la matriz, devuelve el número de elementos de una matriz que consta de los elementos que cumplen el predicado.

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a>Entrada

### <a name="predicate--t---bool"></a>predicado: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)

Función de `'T` a un valor booleano que se usa para filtrar elementos.


### <a name="array--t"></a>matriz: ' t []

Matriz de elementos sobre `'T` .



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Número de elementos de `array` que satisfacen el predicado.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de `array` elementos.

## <a name="remarks"></a>Observaciones

La función se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y un predicado, `'T -> Bool` podemos filtrar elementos.