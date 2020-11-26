---
uid: Microsoft.Quantum.Arrays.Zipped3
title: Zipped3 función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped3
qsharp.summary: Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: 37fda4082a46870270414649f807659fa561962b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219692"
---
# <a name="zipped3-function"></a>Zipped3 función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dadas tres matrices, devuelve una nueva matriz de 3 tuplas, de modo que cada una de estas tres tuplas contiene un elemento de cada matriz original.

```qsharp
function Zipped3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a>Entrada

### <a name="first--t1"></a>primero: ' t 1 []

Una matriz que contiene valores para el primer elemento de cada tupla.


### <a name="second--t2"></a>segundo: ' t 2 []

Una matriz que contiene valores para el segundo elemento de cada tupla.


### <a name="third--t3"></a>tercer: ' t 3 []

Una matriz que contiene valores para el tercer elemento de cada tupla.



## <a name="output--t1t2t3"></a>Salida: (' t 1, ' no 2, ' t 3) []

Una matriz que contiene tres tuplas del formulario `(first[idx], second[idx], third[idx])` para cada una de ellas `idx` . Si las tres matrices no tienen la misma longitud, la salida será tan larga como las entradas más cortas.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t1"></a>' T 1 '

Tipo de los primeros elementos de la matriz.
### <a name="t2"></a>' T 2

Tipo de los elementos de la segunda matriz.
### <a name="t3"></a>No 3

Tipo de los elementos de la tercera matriz.

## <a name="see-also"></a>Consulte también

- [Microsoft.Quantum.Arrays.ZipPED](xref:Microsoft.Quantum.Arrays.Zipped)
- [Microsoft.Quantum.Arrays.Zipped4](xref:Microsoft.Quantum.Arrays.Zipped4)