---
uid: Microsoft.Quantum.Arrays.Transposed
title: Función transpuesta
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729980"
---
# <a name="transposed-function"></a>Función transpuesta

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Configura [](https://nuget.org/packages/)


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