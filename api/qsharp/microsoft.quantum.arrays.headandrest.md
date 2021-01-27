---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: c082e0a917343c18e5f511f065b2e78f1e217ecc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848562"
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