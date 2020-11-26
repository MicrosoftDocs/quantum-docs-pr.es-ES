---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Función enumerada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 94e8fdb7288bc43ed84d10a3292819b455a2be31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221426"
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