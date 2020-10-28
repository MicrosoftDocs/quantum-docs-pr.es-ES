---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: c929054b96ee499db896cacf0e3ae4da6f6c4b98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730149"
---
# <a name="lookupfunction-function"></a>LookupFunction función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Configura [](https://nuget.org/packages/)


Dada una matriz, devuelve una función que devuelve elementos de esa matriz.

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a>Entrada

### <a name="array--t"></a>matriz: ' t []

Matriz que se va a representar como una función de búsqueda.



## <a name="output--int---t"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int) -> ' t

Función `f` tal que `f(idx) == f[idx]` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de los elementos de la matriz que se representa como una función de búsqueda.

## <a name="remarks"></a>Observaciones

Esta función es principalmente útil para interoperar con funciones y operaciones que toman `Int -> 'T` funciones como argumentos. Esto es común, por ejemplo, en la biblioteca de representación del generador, donde las funciones se usan para evitar la necesidad de registrar una matriz completa en la memoria.