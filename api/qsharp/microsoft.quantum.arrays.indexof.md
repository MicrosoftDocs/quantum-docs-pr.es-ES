---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848518"
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



## <a name="example"></a>Ejemplo

Supongamos que `IsEven : Int -> Bool` es una función que devuelve `true` solo si su entrada es par. A continuación, se puede usar con `IndexOf` para buscar el primer elemento par en una matriz:

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```