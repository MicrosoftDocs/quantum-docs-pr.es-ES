---
uid: Microsoft.Quantum.Arrays.Transposed
title: Función transpuesta
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 913f1829ef53ec3eb6944be8b8e3eb37b431f27e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850931"
---
# <a name="transposed-function"></a>Función transpuesta

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve la transposición de una matriz representada como una matriz de matrices.

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a>Descripción

Entrada como $r \times c $ Matrix con $r $ Rows y $c $ Columns.  La matriz está basada en filas; es decir, `matrix[i][j]` tiene acceso al elemento de la fila $i $ y a la columna $j $.

Esta función devuelve la matriz $c \times r $ que es la transformación de la matriz de entrada.

## <a name="input"></a>Entrada

### <a name="matrix--t"></a>matriz: ' t [] []

$R basado en filas \times c $ Matrix



## <a name="output--t"></a>Salida: ' t [] []

$C \times r $ Matrix

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de cada elemento de `matrix` .

## <a name="example"></a>Ejemplo

```qsharp
// same as [[1, 4], [2, 5], [3, 6]]
let transposed = Transposed([[1, 2, 3], [4, 5, 6]]);
```