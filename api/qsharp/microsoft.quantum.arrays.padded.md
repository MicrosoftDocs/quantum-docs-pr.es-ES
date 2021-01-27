---
uid: Microsoft.Quantum.Arrays.Padded
title: Función acolchada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845561"
---
# <a name="padded-function"></a>Función acolchada

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Ejemplo

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```