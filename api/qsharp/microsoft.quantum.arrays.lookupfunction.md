---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: 22b56bb7e9f03ebc5b2225efb2e6450d56022664
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845699"
---
# <a name="lookupfunction-function"></a>LookupFunction función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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