---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 32dc814de9b04563c2798a768f121723a1a8252c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846252"
---
# <a name="columnat-function"></a>ColumnAt función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Ejemplo

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let column = ColumnAt(0, matrix);
// same as: column = [1, 4, 7]
```

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. matrices. transpuesto](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft. Quantum. matrices. Diagonal](xref:Microsoft.Quantum.Arrays.Diagonal)