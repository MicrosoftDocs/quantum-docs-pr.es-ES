---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 8ed658003f749efd31b8d841cecbb0a23a471af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850897"
---
# <a name="zip-function"></a>Zip (función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> Zip está en desuso. Use <xref:Microsoft.Quantum.Arrays.Zipped> en su lugar.

Dadas dos matrices, devuelve una nueva matriz de pares de modo que cada par contiene un elemento de cada matriz original.

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a>Entrada

### <a name="left--t"></a>Left: ' t []

Una matriz que contiene valores para el primer elemento de cada tupla.


### <a name="right--u"></a>Right: ' U []

Una matriz que contiene valores para el segundo elemento de cada tupla.



## <a name="output--tu"></a>Salida: (' t, ' U) []

Una matriz que contiene pares del formulario `(left[idx], right[idx])` para cada `idx` . Si las dos matrices no tienen la misma longitud, la salida será tan larga como las entradas más cortas.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de los elementos de la matriz izquierda.
### <a name="u"></a>' U

Tipo de los elementos de la matriz de la derecha.

## <a name="example"></a>Ejemplo

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zip(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a>Consulte también

- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)
- [Microsoft. Quantum. matrices. descomprimido](xref:Microsoft.Quantum.Arrays.Unzipped)