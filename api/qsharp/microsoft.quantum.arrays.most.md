---
uid: Microsoft.Quantum.Arrays.Most
title: La mayoría de las funciones
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 2b212b38ec55f3798eb9397f03b842573173eb88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845575"
---
# <a name="most-function"></a>La mayoría de las funciones

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crea una matriz que es igual a una matriz de entrada, salvo que se quita el último elemento de la matriz.

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="array--t"></a>matriz: ' t []

Matriz cuyo primer y último elemento se van a mostrar en la matriz de salida.



## <a name="output--t"></a>Salida: ' t []

Una matriz que contiene los elementos `array[0..Length(array) - 2]` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

El tipo de los elementos de la matriz.