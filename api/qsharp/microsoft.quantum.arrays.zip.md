---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 32fea60fc36bfdbaa2ab2f3560f291bf4ce4fa51
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729924"
---
# <a name="zip-function"></a>Zip (función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Configura [](https://nuget.org/packages/)


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

## <a name="see-also"></a>Consulte también

- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)
- [Microsoft. Quantum. matrices. descomprimido](xref:Microsoft.Quantum.Arrays.Unzipped)