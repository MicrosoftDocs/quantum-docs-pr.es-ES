---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Función diagonal
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 180b7185c94d712fa02100cb97abfbb6c464d12a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730357"
---
# <a name="diagonal-function"></a>Función diagonal

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Configura [](https://nuget.org/packages/)


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