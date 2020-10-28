---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: ad09ada1a2253a54e70dddd6dba8aa243d2cd5a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730405"
---
# <a name="columnat-function"></a>ColumnAt función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Configura [](https://nuget.org/packages/)


Extrae una columna de una matriz.

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Descripción

Esta función extrae una columna de una matriz en orden de fila.
Extraer una fila corrsponds al acceso a elementos del primer índice y, por lo tanto, no requiere ningún tratamiento adicional.

## <a name="input"></a>Entrada

### <a name="column--int"></a>columna: [int](xref:microsoft.quantum.lang-ref.int)

Columna de la matriz


### <a name="matrix--t"></a>matriz: ' t [] []

matriz bidimensional en orden de fila



## <a name="output--t"></a>Salida: ' t []



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de cada elemento de `matrix` .

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. matrices. transpuesto](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft. Quantum. matrices. Diagonal](xref:Microsoft.Quantum.Arrays.Diagonal)