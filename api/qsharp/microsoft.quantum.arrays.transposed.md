---
uid: Microsoft.Quantum.Arrays.Transposed
title: Función transpuesta
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: f293399d8e3a2cb32b2929e8d1591ac5eaefd277
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219998"
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