---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 1144e00227df1cd7d96bc76b118b0b556adbaa96
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221086"
---
# <a name="headandrest-function"></a>HeadAndRest función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve una tupla del primer y el resto de elementos de la matriz.

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a>Entrada

### <a name="array--a"></a>matriz: ' A []

Matriz con al menos un elemento.



## <a name="output--aa"></a>Salida: (' A, ' A [])

Tupla del primer y de todos los elementos restantes de la matriz.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="a"></a>' A '

El tipo de los elementos de la matriz.