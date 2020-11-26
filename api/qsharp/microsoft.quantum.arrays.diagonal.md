---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Función diagonal
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: fe6bac0acfa07b14620c7c35ae5e1cec2287d13d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221545"
---
# <a name="diagonal-function"></a>Función diagonal

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve una matriz de elementos diagonales de una matriz bidimensional.

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Descripción

Si la matriz bidimensional no tiene una forma cuadrada, se devolverá la diagonal sobre el número mínimo de filas y columnas.

## <a name="input"></a>Entrada

### <a name="matrix--t"></a>matriz: ' t [] []

matriz bidimensional en orden de fila



## <a name="output--t"></a>Salida: ' t []



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de cada elemento de `matrix` .

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. matrices. transpuesto](xref:Microsoft.Quantum.Arrays.Transposed)