---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: d63b204334611f8f2c3860f9ee1d756f637780e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221018"
---
# <a name="indexof-function"></a>IndexOf (función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve el primer índice del primer elemento de una matriz que satisface un predicado determinado. Si no existe ningún elemento de este tipo, devuelve-1.

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a>Entrada

### <a name="predicate--t---bool"></a>predicado: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)

Función de predicado que actúa sobre los elementos de la matriz.


### <a name="arr--t"></a>ARR: ' t []

Matriz en la que se va a buscar mediante el predicado especificado.



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

El índice más pequeño, `idx` tal que `predicate(arr[idx])` sea true, o-1 si no existe ese elemento.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

