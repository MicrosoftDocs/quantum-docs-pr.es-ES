---
uid: Microsoft.Quantum.Arrays.Reversed
title: Función invertida
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 50699465711de45ff994095e6c098550d637d608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845456"
---
# <a name="reversed-function"></a>Función invertida

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Cree una matriz que contenga los mismos elementos que una matriz de entrada, pero en orden inverso.

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="array--t"></a>matriz: ' t []

Una matriz cuyos elementos se van a copiar en orden inverso.



## <a name="output--t"></a>Salida: ' t []

Una matriz que contiene los elementos `array[Length(array) - 1]` . `array[0]`.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

El tipo de los elementos de la matriz.