---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Función enumerada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848121"
---
# <a name="enumerated-function"></a>Función enumerada

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una matriz, devuelve una nueva matriz que contiene elementos de la matriz original junto con los índices de cada elemento.

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a>Entrada

### <a name="array--telement"></a>matriz: ' Telement []

Una matriz cuyos elementos se van a enumerar.



## <a name="output--inttelement"></a>Salida: ([int](xref:microsoft.quantum.lang-ref.int), ' telement) []

Nueva matriz que contiene los elementos de la matriz original junto con sus índices.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="telement"></a>' TEle

Tipo de elementos de la matriz.

## <a name="example"></a>Ejemplo

Los `for` bucles siguientes son equivalentes:

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```