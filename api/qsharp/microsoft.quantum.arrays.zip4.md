---
uid: Microsoft.Quantum.Arrays.Zip4
title: Zip4 función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: d42b3b6db059163f6c766d4f133551be293c153d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729901"
---
# <a name="zip4-function"></a>Zip4 función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Configura [](https://nuget.org/packages/)


> [!WARNING]
> Zip4 está en desuso. Use <xref:Microsoft.Quantum.Arrays.Zipped4> en su lugar.

Dadas cuatro matrices, devuelve una nueva matriz de 4 tuplas, de modo que cada tupla de 4 contiene un elemento de cada matriz original.

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a>Entrada

### <a name="first--t1"></a>primero: ' t 1 []

Una matriz que contiene valores para el primer elemento de cada tupla.


### <a name="second--t2"></a>segundo: ' t 2 []

Una matriz que contiene valores para el segundo elemento de cada tupla.


### <a name="third--t3"></a>tercer: ' t 3 []

Una matriz que contiene valores para el tercer elemento de cada tupla.


### <a name="fourth--t4"></a>cuarto: ' t 4 []

Una matriz que contiene valores para el cuarto elemento de cada tupla.



## <a name="output--t1t2t3t4"></a>Salida: (' t 1, ' no 2, ' t 3, ' t 4 ') []

Una matriz que contiene cuatro tuplas del formulario `(first[idx], second[idx], third[idx], fourth[idx])` para cada una de ellas `idx` . Si las cuatro matrices no tienen la misma longitud, la salida será tan larga como las entradas más cortas.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t1"></a>' T 1 '

Tipo de los primeros elementos de la matriz.
### <a name="t2"></a>' T 2

Tipo de los elementos de la segunda matriz.
### <a name="t3"></a>No 3

Tipo de los elementos de la tercera matriz.
### <a name="t4"></a>No 4

El tipo de los cuatro elementos de la matriz.

## <a name="see-also"></a>Consulte también

- [Microsoft.Quantum.Arrays.Zip](xref:Microsoft.Quantum.Arrays.Zip)
- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)