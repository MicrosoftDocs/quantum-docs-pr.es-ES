---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: EmptyArray función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846170"
---
# <a name="emptyarray-function"></a>EmptyArray función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Devuelve la matriz vacía de un tipo determinado.

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a>Salida: ' Telement []

Matriz vacía.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="telement"></a>' TEle

Tipo de elementos de la matriz.

## <a name="example"></a>Ejemplo

```qsharp
let empty = EmptyArray<Int>();
```