---
uid: Microsoft.Quantum.Arrays.Padded
title: Función acolchada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 8742d4726e7ee32349bf3d0bd5077352ffca350b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730092"
---
# <a name="padded-function"></a>Función acolchada

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Configura [](https://nuget.org/packages/)


Devuelve una matriz que se rellena con los valores especificados hasta una longitud especificada.

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="nelementstotal--int"></a>nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)

Longitud de la matriz rellenada. Si es positivo, `inputArray` se rellena en el encabezado. Si es negativo, `inputArray` se rellena en la cola.


### <a name="defaultelement--t"></a>defaultElement: ' t

Valor predeterminado que se va a usar para los elementos de relleno.


### <a name="inputarray--t"></a>inputArray: ' t []

Matriz cuyos valores están en el encabezado de la matriz de salida.



## <a name="output--t"></a>Salida: ' t []

Una matriz `output` que es el `inputArray` rellenado en el encabezado con `defaultElement` s hasta que `output` tiene la longitud `nElementsTotal`

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

El tipo de los elementos de la matriz.